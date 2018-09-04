---
layout: post
title:  "Install R Kernel on SageMaker"
date:   2018-07-28 21:32:32 -0700
categories: AWS SageMaker
---

Do you want to program in R on AWS SageMaker Jupyter Notebook?

Here are the steps to install R Kernel:

1. Create a new notebook.  Choose "conda_python2".  

2. Run the following Python command.  It will install an R kernel to your notebook instance.  
The install takes approximately 5 mins to complete.
{% highlight ruby %}
!conda install --yes --name JupyterSystemEnv --channel r r-essentials=1.6.0
{% endhighlight %}

Once the install is finished, there's a long output, which includes a list of installed R libraries.

![Install complete screenshot](https://lynnaj.github.io/datacadabra/assets/sagemaker_r_install_done.jpg)

3. Close the notebook instance & reopen the notebook from SageMaker console.

4. Now, you should see R available as one of many notebooks options.

Here is my source: [AWS SageMaker Docs][rinstallsagemaker-docs].  
AWS' instructions are a bit different.  They suggest executing the above code (without the exclamation sign) in terminal, instead of a notebook.

[rinstallsagemaker-docs]: https://docs.aws.amazon.com/sagemaker/latest/dg/nbi-add-external.html