Continual Learning Model Back-end APIs
======================================

Our continual learning back-end contains a GAPS model, a VOS model, and a memory replay buffer.

app.py 
------

This file is our flask back-end. it contains REST APIs we need.

.. py:function:: gen_frames_with_pred()

    this function is a helper function which continuously yield predicted frame to our API

    it will trigger ``my_trainer.infer_one_aot()`` which will generate a predicted frame


.. py:function:: get_pred_cam_stream()

    front-end could use ``http://127.0.0.1:7000/pred_cam`` to GET the frame stream from continual learning back-end server.

    Flask API function. this function continuously yield predicted frame.

    :return: Flask Response that contains predict frame

    :rtype: Flask Response object


.. py:function:: gen_frames()

    this function is a helper function which continuously yield original camera frame to our API

    Note: this function is for debug purpose.


.. py:function:: get_camera_stream()

    front-end could use ``http://127.0.0.1:7000/camera`` to GET the frame stream from continual learning back-end server.

    Flask API function. this function continuously yield original camera frame.

    :return: Flask Response that contains original camera frame

    :rtype: Flask Response object


.. py:function:: take_snapshot()

    front-end could use ``http://127.0.0.1:7000/snapshot`` to GET a snapshot from camera.

    Flask API function. this function return a image by base64 string.

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

.. py:function:: undo_finetune()

    front-end could use ``http://127.0.0.1:7000/undo`` to trigger our continual learning model restore the last state (forget the last object it learned)

    Flask API function. this function return the undo status.

    :return: response json string that return the status of API.

    :rtype: JSON object

    Return Format:
    
    .. code-block::

        {
            status: "success"
        }

.. py:function:: trigger_fine_tune()

    front-end could use ``http://127.0.0.1:7000/trigger_finetune`` to trigger our continual learning model start to adapt a novel object.

    Flask API function. this function return the adaptation status.

    Request Format:

    .. code-block::

        resp = requests.post("http://localhost:7000/trigger_finetune",
                    files={"file": img_bytes, "mask": mask_bytes, "label":label})
        files:
        {
            "file": "SDJFOIDS87x..." (pickle),
            "mask": "[[True False True True .....]]" (pickle) 
            "label": "car" (bytes)
        }

    :return: response json string that return the status of API.

    :rtype: JSON object

    Return Format:
    
    .. code-block::

        {
            status: "success"
        }
