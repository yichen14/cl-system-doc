Start to Use the System
=======================

Running
-------
Please run these 3 different commands separately in the specified path:
    1. Check out to the path of ``cl_ritm_backend/ritm-backend/`` and run the following command:
        .. code-block:: console

            $ python3 app.py
    
    2. Check out to the path of ``cl_system`` and run the following command:
        .. code-block:: console

            $ python3 main/web_app.py --cfg ./web_app.yaml

    3. Check out to the path of ``cl_frontend`` and run the following command:
        .. code-block:: console

            $ npm start

After running the commands above, you will see a html webpage poped up like this:
    .. image:: pic1.png
        :width: 400
        :alt: Alternative text

Training
--------
Our system could recognize 20 objects by default: 'wall', 'floor', 'cabinet', 'bed', 'chair', 'sofa', 'table', 'door', 'window', 'bookshelf', 'picture', 'counter', 'desk', 'curtain', 'refrigerator', 'shower curtain', 'toilet', 'sink', 'bathtub', 'otherfurniture'.

In order to train the system to recognize other objects, here are some steps you need to do:

    1. Move the camera towards the objects you would like to recognize.

    2. Click ``take the snapshot``, and you will see an image like this:
        .. image:: pic2.png
            :width: 400
            :alt: Alternative text

    3. Then click the positive button and then click the object that you would like to make the system recognize. You can make multiple clicks on your object to make sure the system could fully mask the object.
        .. image:: pic3.png
                :width: 400
                :alt: Alternative text
    4. If you or the system wrongly labled an area, you can click ``negative`` and then click the place you or the system wrongly labled like this:
        .. image:: pic4.png
                :width: 400
                :alt: Alternative text

        .. image:: pic5.png
            :width: 400
            :alt: Alternative text

        .. image:: pic6.png
            :width: 400
            :alt: Alternative text

    5. Finally, you can click start fine-tune model to train it.