# BlazePose for the [OAK-D](https://docs.luxonis.com/projects/hardware/en/latest/pages/BW1098OAK.html)

---
**intro**

assorted routines to fetch google's mediapipe [pose](https://google.github.io/mediapipe/solutions/pose.html) (detection and landmarks) models
and convert them to onnx and myriad X blob formats

---
**overview of the main steps to replicate procedure**

* create virtual enviroment

* install *requirements.txt* (tensorflow and tflite-runtime will fail)

* install custom tensorflow and tflite-runtime from https://github.com/PINTO0309/tflite2tensorflow

> $ sudo pip3 uninstall tensorboard-plugin-wit tb-nightly tensorboard \
>                       tf-estimator-nightly tensorflow-gpu \
>                       tensorflow tf-nightly tensorflow_estimator tflite_runtime -y
> 
> $ APPVER=v1.10.0
> $ TENSORFLOWVER=2.6.0rc1
> 
> ### Customized version of TensorFlow Lite installation
> $ wget https://github.com/PINTO0309/tflite2tensorflow/releases/download/${APPVER}/tflite_runtime-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && sudo chmod +x tflite_runtime-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && pip3 install --user --force-reinstall tflite_runtime-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && rm tflite_runtime-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl
> 
> ### Install the Customized Full TensorFlow package
> ### (MediaPipe Custom OP, FlexDelegate, XNNPACK enabled)
> $ wget https://github.com/PINTO0309/tflite2tensorflow/releases/download/${APPVER}/tflite_runtime-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && sudo chmod +x tensorflow-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && pip3 install --user --force-reinstall tensorflow-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl \
>   && rm tensorflow-${TENSORFLOWVER}-cp36-none-linux_x86_64.whl

* check variables in the *do_stuff.sh* file and adapt accordingly 

* call *do_stuff.sh*

---
