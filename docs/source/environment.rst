Environment Setup
=================

Our system have three different components:
    - React front-end
    - RITM back-end
    - continual learning back-end

This three components could be deployed on different machine or you can also run these components on single machine.

Get Source Code
----------------
    1. React front-end:
        .. code-block:: console

            $ git clone https://github.com/yichen14/continual-learning-system.git
    2. RITM back-end:
        .. code-block:: console

            $ git clone https://github.com/yichen14/cl_ritm_backend.git
            
    .. $ git clone -b origin/eason/tools https://github.com/RogerQi/dl_codebase.git

    3. continual learning back-end:
        .. code-block:: console

            
            $ git clone https://github.com/wangzikui123/cl_system.git

        
        inside the ``cl_system/main`` folder:
            .. code-block:: console

                $ git clone https://github.com/RogerQi/vision_hub.git

        inside the ``cl_system/main/vision_hub/vos`` 
            .. code-block:: console

                $ git clone https://github.com/yoxu515/aot-benchmark.git



Required Packages
-----------------
    Please install the packages used in our system by running:
        .. code-block:: console

            $ pip install -r requirements.txt



Required Pretrained Weights
---------------------------
    You should first go to https://drive.google.com/drive/folders/14Qx7e5F_Q7uWZYSOGnXr1adpQqrBScme?usp=sharing to download the pre-trained weights for the whole system.

    There will be 4 pre-trained weights files inside 3 folders of ``ritm``, ``cl_system`` and ``aotb`` in the shared link above.

    Please put each of these pre-trained weights into the following files:

    1. put the pretrained weights files in ``cl_system`` folder to your local path of ``cl_system/``

    2. put the pretrained weights files in ``aotb`` folder to your local path of ``cl_system/main/vision_hub/vos/aot-benchmark/pretrain_models/``

    .. 3. put the pretrained weights in ``ritm`` to your local path of ``cl_system``
