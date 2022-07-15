RITM Back-end APIs
===================

Our ritm backend worked for interactive segmentation function in our system. It can automatically generate the mask by few clicks.

app.py 
------

This file is our flask back-end. it contains REST APIs we need.

.. py:function:: click()

   To click on the image, front-end could POST a request to ``localhost:5000/click``

   Flask API function. provide a click on annotating image. Return the base64 image string through json

   Request Format:

   .. code-block::

      {
         "click":{
            "is_postive": true,
            "coords_x": 220,
            "coords_y": 160
         } 
      }

   :return: response json string which contains base64 image string.

   :rtype: JSON object

   Return Format:
   
   .. code-block::

      {
         data:{
            img: (image base64 string)
         } 
         status: 200
         statusText: "OK"
      }

.. py:function:: train_single()

   To trigger the adaptation process in our continual learning back-end, front-end could POST a request to ``localhost:5000/train``

   Flask API function. this function post a request to our continual learning back-end server to trigger finetune process.

   Request Format:

   .. code-block::

      {
         "label":mask_label e.g."homepod"
      }

   :return: response json string from the continual learning back-end server

   :rtype: JSON object

   Return Format:
   
   .. code-block::

      {
         status: "success"
      }
  

.. py:function:: add_img()

   To add a new image to ritm segmentation server, front-end could POST a request to ``localhost:5000/addimg``

   Flask API function. front-end post the image that need to be annotated to the ritm back-end

   Request Format:

   .. code-block::

      { 
        data: img,
        headers: {
          'Content-Type': 'multipart/form-data'
        }
      }

   :return: response json string that return the status of API.

   :rtype: JSON object

   Return Format:
   
   .. code-block::

      {
         status: "success"
      }

.. py:function:: get_annotating_img()

   To get the original image from ritm server, front-end could have a GET request to ``localhost:5000/getimg``

   Flask API function. this function is mainly for debug purpose. front-end could get the original image (don't have annotation mask) from ritm back-end server.

   :return: response json string which contains base64 image string.

   :rtype: JSON object

   Return Format:
   
   .. code-block::

      {
         data:{
            img: (image base64 string)
         } 
         status: 200
         statusText: "OK"
      }

handle_click.py
---------------

.. py:function:: get_prediction_from_click()

   this is a helper function that handle the "click" data and send click to the ritm model.

   :param predictor: Required the ritm model predictor

   :type predictor: ritm predictor object

   :param single_click: Required a single click information which contains click position and click type.

   :type single_click: ritm Click object

   :param pred_thr: Optional ritm model predict threshold, default is 0.49

   :type pred_thr: float

   :return: click_list: the list of clicks; iou_list; pred_mask: the annotation we need.

   :rtype: list[Click], Numpy Array[np.float32], list[list[bool]]
