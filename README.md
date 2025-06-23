# train-a-model-with-SageMaker-Lab
Guide and code to train a model using SageMaker and Python

Train a model with Amazon SageMaker
SPL-TF-300-MLMLMD-1 - Version 1.0.4

© 2025 Amazon Web Services, Inc. or its affiliates. All rights reserved. This work may not be reproduced or redistributed, in whole or in part, without prior written permission from Amazon Web Services, Inc. Commercial copying, lending, or selling is prohibited. All trademarks are the property of their owners.

Note: Do not include any personal, identifying, or confidential information into the lab environment. Information entered may be visible to others.

Corrections, feedback, or other questions? Contact us at AWS Training and Certification.

Lab Overview
AnyCompany Consulting has received data from the nonprofit advocacy group and has prepared the dataset for training. As the data scientist for AnyCompany Consulting, you now need to train the machine learning (ML) model and evaluate the results. Because the label feature that you are trying to predict on is a binary classification (less than $50,000 or not), you need to choose an ML algorithm that can work on binary classification problems. To this end, you will configure and train a model based on SageMaker’s built-in XGBoost, then you will evaluate the prediction efficiency of the model.

You also need to explore a more custom scenario. To this end, you will configure a custom model built on the XGBoost framework. By running XGBoost as a framework inside SageMaker, you have more flexibility and access to more advanced scenarios, such as k-fold cross-validation, because you can customize your own training scripts.

Objectives
By the end of this lab, you should be able to do the following:

Train a model using built-in SageMaker Algorithms.
Understand how to write custom training and inference code while still using common ML frameworks maintained by AWS.
Understand how to Import custom libraries and dependencies to train your model.
Understand how to setup a Hyperparameter Tuning Job in SageMaker.
Icon key
Various icons are used throughout this lab to call attention to different types of instructions and notes. The following list explains the purpose for each icon:

 Caution: Information of special interest or importance (not so important to cause problems with the equipment or data if you miss it, but it could result in the need to repeat certain steps).
 Warning: An action that is irreversible and could potentially impact the failure of a command or process (including warnings about configurations that cannot be changed after they are made).
 Learn more: Where to find more information.
 Note: A hint, tip, or important guidance.
 Task complete: A conclusion or summary point in the lab.
Start lab
To launch the lab, at the top of the page, choose Start Lab.

 Caution: You must wait for the provisioned AWS services to be ready before you can continue.

To open the lab, choose Open Console .

You are automatically signed in to the AWS Management Console in a new web browser tab.

 Warning: Do not change the Region unless instructed.

Common sign-in errors
Error: Choosing Start Lab has no effect
In some cases, certain pop-up or script blocker web browser extensions might prevent the Start Lab button from working as intended. If you experience an issue starting the lab:

Add the lab domain name to your pop-up or script blocker’s allow list or turn it off.
Refresh the page and try again.
Lab environment
The following diagram shows the basic architecture of the lab environment:

The architecture diagram of the lab environment.

Image description: The preceding diagram depicts an Amazon Simple Storage Service (Amazon S3) bucket with the processed training data. A Jupyter notebook with training code uses a training container image from an Amazon ECR Repository of SageMaker container images. The notebook code creates a model and stores the model in another Amazon S3 bucket.

AWS services not used in this lab
AWS service capabilities used in this lab are limited to what the lab requires. Expect errors when accessing other services or performing actions beyond those provided in this lab guide.

Task 1: Train a model using a built-in algorithm
In this task, you first launch a SageMaker Studio application. Then you configure an estimator object and hyperparameters, run a SageMaker training job, and evaluate the model.

Task 1.1: Set up the environment
Copy the SageMakerStudioUrl value that is listed to the left of these instructions.

Open a new browser tab, and then paste the SageMakerStudioUrl into the address bar.

Press Enter.

A new browser tab opens, taking you to the JuypterLab workspaces interface.

 Note: It might take 1-2 minutes for the JupyterLab workspaces interface to load for the first time.

Next, clone a Git repository and open the lab repository folder.

In the left menu bar, choose the Git icon.

Choose Clone a Repository.

The SageMaker Studio environment displays the Clone Git Repository window.

For Git repositories URL(.git):, copy and paste the CloneUrlForRepo value listed to the left of these instructions, and select the suggested url from the drop-down menu.

Choose Clone.

Wait for the repository cloning to complete.

The SageMaker Studio environment opens the MLMLMD_Repository folder when the clone completes.

 Task complete: You have successfully launched SageMaker Studio and cloned a Git repository into the environment.

Task 1.2: Train the model
In the left navigation pane, open the train_built_in.ipynb notebook.

On the Select Kernel pop-up window, for Select kernel for: parameter, choose Python 3 (ipykernel).

Choose Select.

 Note: It might take 1–2 minutes for the kernel to load.

Carefully advance through the train_built_in.ipynb notebook. Run each code cell and review the completed output. To run a cell, select within the cell and press Shift + Enter or, at the top of the page, choose the Run button. An asterisk appears next to the code block while it runs.
 Task complete: When you have finished running the notebook, you can return here to move to the next task.

Task 2: Train a model using a custom script in script-mode
In this task, you once again train a model, but this time using a customized script and the SageMaker script-mode.

In the left navigation pane of the SageMaker Studio environment, open the train_script_mode.ipynb notebook.

On the Select Kernel pop-up window, for Select kernel for: parameter, choose Python 3 (ipykernel).

Choose Select.

 Note: It might take 1–2 minutes for the kernel to load.

Carefully advance through the train_script_mode.ipynb notebook. Run each code cell and review the completed output. To run a cell, select within the cell and press Shift + Enter or, at the top of the page, choose the Run button. An asterisk appears next to the code block while it runs.
 Task complete: When you have finished running the notebook, you can return here to finish the lab.

Conclusion
You have successfully done the following:

Trained a model using built-in SageMaker Algorithms.
Understood how to write custom training and inference code while still using common ML frameworks maintained by AWS.
Understood how to Import custom libraries and dependencies to train your model.
Understood how to setup a Hyperparameter Tuning Job in SageMaker.
End lab
Follow these steps to close the console and end your lab.

Return to the AWS Management Console.

At the upper-right corner of the page, choose AWSLabsUser, and then choose Sign out.

Choose End Lab and then confirm that you want to end your lab.
