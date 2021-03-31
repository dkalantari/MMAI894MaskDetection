# Face Mask Detection
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dkalantari/MMAI894MaskDetection/blob/main/Notebooks/894_Bremner_Mask_Detection_ScaledYOLOv4.ipynb)  
##### Face Mask Detection system built with Keras/TensorFlow using Transfer Learning Scaled YOLOv4 model and Computer Vision concepts in order to detect mask or non-mask wearing  in static images as well as in videos.
#
#
[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)    [![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)


## Introduction

No event in recent history has had a more drastic impact on our personal, professional, and social lives than COVID-19. The global economy has gone through cycles of workplace shutdowns and has relied heavily on its digital infrastructure to continue functioning. Many day-to-day functions such as restaurants, hair salons, and retail stores have been brought down to bare essential services. While many businesses did not survive, many were able to adapt and utilize the economy’s digital infrastructure to continue their operations during the last year. Despite substantial research to understand the virus and ways to battle it, the three main modes for slowing this virus remain the same: wash hands often, wear masks, and ultimately get vaccinated. While vaccination is the ultimate way to end this pandemic return to normalcy, in the short-term and medium-term the consensus among all top health organizations is that we need to wear masks to prevent the spread of the virus even after receiving the vaccines to prevent those in danger. 
Bremner Inc. was approached by several large private and public organizations including airports, banks, and shopping malls, to develop a means for monitoring mask wearing compliance

## Business Solution 
Our team have come-up with a solution that would provide the clients with a process to monitor whether the employees and visitors who enter the business premises are obliging with the COVID-19 protocols. Our solution involves training an object-detection model on an image dataset consisting of individual faces which are annotated with labels “mask” and “no-mask” using bounding-boxes. Once the model is trained with such images and is capable of detecting the individual faces in frames and classifying them as mask-wearing versus non-mask-wearing, it can be deployed either directly to edge devices or hosted API for real-life use. 

## Installation of Code

To run our code it is best to use the Google Colab resources as the training will require high GPU processing. Simply, clone this repo and upload to a Colab instance:

```sh
git clone https://github.com/dkalantari/MMAI894MaskDetection.git
```
Or for quick implementation, simply hit the 'Open in Colab' at the top of this page or link below, and once opened Colab make sure to Save a Copy in Drive:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dkalantari/MMAI894MaskDetection/blob/main/Notebooks/894_Bremner_Mask_Detection_ScaledYOLOv4.ipynb)  
```sh
File ->  'Save a Copy in Drive'
Runtime -> 'Run All'
```




## Data Collection and Preprocessing
With the goal of mask-detection in video frames, we knew our data should be made of two types of images: people who wear masks and people who did not wear masks. In order for our model to generalize to the appropriate backgrounds and demographics in real-life application, we decided to do a strategic data collection containing a diverse set of people and also a diverse set of locations. We then pre-processed the collected images using a computer vision platform called RoboFlow and used the pre-processed data to test our model’s performance. We repeated the process until we achieved an acceptable performance score with our model.

### Data Collection Summary

During a two weeks long collective effort by everyone in the team, we finalized our dataset with 1815 images made of 3751  “mask” labels and 6148 “no-mask” labels achieving the highest number of labels in all four iterations


## Modelling
Since we are only interested in the task of object-detection and not object segmentation, we narrowed down our selection to a handful of object-detection families from which we only focused on the group of single-shot detectors. In the report will provide a recap of our model design process that led to our decision of picking Scaled-YOLOv4-CSP as our main model.


### Classification model: Choice of architecture

Transfer learning was employed to use the model weights of the Scaled-YOLOv4 model.
Learning hyperparameters such as learning rate were chosen in an iterative manner, with recommendations taken on choices of values based on available architecture.


![Object Detection](https://i.ibb.co/0tHfFgg/object-dection1.png)

## Criterion for evaluation: Precision & mAP

The Average Precision (AP) or Mean Average Precision (mAP) is averaged over all categories. There is no distinction between AP and mAP. AP (averaged across all 10 IoU thresholds an over the 2 categories). This was considered the single most important metric when considering performance with respect to the measuring against the SOTA using the COCO dataset with has over 330,000 val2017 format images.

## Results of Model

Figure below shows after several iterations our model’s average precision score with a recall more than 80% allowing it to capture most ground truth object while not being too imprecise in classifying them.

![Object Detection](https://i.ibb.co/TLTTDFs/fig22-good-on-groundtruth.jpg)

Our experimentation with increasing the number of epochs pushed the model to perform considerably better than only 25 epochs as it allowed the model to have higher passes through a considerably bigger dataset and therefore optimize the weights more effectively by gathering more features from each training batch.
![Tensorbaord_results](https://i.ibb.co/XFp5xNb/tensorboard-result1.jpg)

Video Inferencing results from final model achieving over mAP > 75%:

[![Crowd Inference](https://i.ibb.co/m9bC9Qs/team-bef-aft2.gif)
[![Crowd Inference](https://i.ibb.co/096hK0L/crowd-bef-aft.gif)
[![Crowd Inference](https://i.ibb.co/8gM4PtN/group-bef-aft.gif)

## Conclusion & Future Implementation



## Team Contributors

Bremner Inc. is a multinational professional consulting firm specialized in the field of computer vision. We provide end-to-end computer vision solutions which are tailored to solve complex business problems and help our clients achieve their goals through the use of AI. Below are the team members that helped implement this project:

| Name | Role |
| ------ | ------ |
| Dara Kalantari  | Project Manager |
| Moiz Zafar | Business Consultant |
| Devin Datt | Machine Learning Engineer |
| Yi Liu    | Machine Learning Engineer |
| Milind | Data Scientist |
| Paul Longo | Data Scientist |
| Tianchen (Ray) Guo  | Data Scientist |




## ========IGNORE BELOW- NEED EDITING ===========
- Import a HTML file and watch it magically convert to Markdown
- Drag and drop images (requires your Dropbox account be linked)
- Import and save files from GitHub, Dropbox, Google Drive and One Drive
- Drag and drop markdown and HTML files into Dillinger
- Export documents as Markdown, HTML and PDF

Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually- written in Markdown! To get a feel
for Markdown's syntax, type some text into the left window and
watch the results in the right.

## Face Mask Detection

Dillinger uses a number of open source projects to work properly:

- [AngularJS] - HTML enhanced for web apps!
- [Ace Editor] - awesome web-based text editor
- [markdown-it] - Markdown parser done right. Fast and easy to extend.
- [Twitter Bootstrap] - great UI boilerplate for modern web apps
- [node.js] - evented I/O for the backend
- [Express] - fast node.js network app framework [@tjholowaychuk]
- [Gulp] - the streaming build system
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML
to Markdown converter
- [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

## Installation

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd dillinger
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:

```sh
node app
```

Second Tab:

```sh
gulp watch
```

(optional) Third:

```sh
karma test
```

#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd dillinger
docker build -t <youruser>/dillinger:${package.json.version} .
```

This will create the dillinger image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=dillinger <youruser>/dillinger:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```

## License

MIT

**Free Software, Hell Yeah!**

Dillinger is a cloud-enabled, mobile-ready, offline-storage compatible,
AngularJS-powered HTML5 Markdown editor.

- Type some Markdown on the left
- See HTML in the right
- ✨Magic ✨

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
