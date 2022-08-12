Environment Setup
=================

Our system have three different components:
    - React front-end
    - RITM back-end
    - continual learning back-end

This three components could be deployed on different machine or you can also run these components on single machine.

Get Source Code
----------------
    .. code-block:: console

        $ git clone https://github.com/wangzikui123/continual-learning-system.git --recurse-submodules
    
Required Packages
-----------------
    Please install the packages used in our system by running:
        .. code-block:: console

            $ pip install -r requirements.txt



Required Pretrained Weights
---------------------------
    You should first go to https://drive.google.com/drive/folders/14Qx7e5F_Q7uWZYSOGnXr1adpQqrBScme?usp=sharing to download the pre-trained weights for the whole system.

    There will be 4 pre-trained weights files inside 3 folders of ``ritm``, ``cl_system`` and ``aotb`` in the shared link above.

    Please put them into the folder ``continual-learning-system/cl_system/weights``

