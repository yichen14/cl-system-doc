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
    3. continual learning back-end:
        .. code-block:: console

            $ git clone -b origin/eason/tools https://github.com/RogerQi/dl_codebase.git

            $ git clone https://github.com/RogerQi/vision_hub.git

Required Packages
-----------------
    You should first set up your environment for each components based on their original repo's settings in 'requirements.txt'.

    Our back-end components are based on Python-Flask
    
    Our front-end is based on React.js

