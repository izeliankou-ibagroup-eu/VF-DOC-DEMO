# Pipeline Execution

If you run a pipeline, as in the above example, its status changes from *Draft* to *Pending* and then to *Running*. 
Push Refresh to update the status.
The border of the stage currently running is painted in *Blue*:
While running a pipeline can be stopped or suspended with *Stop/Suspend* buttons respectively: ![](../../assets/user-guide-img/image86.png)

![](../../assets/user-guide-img/image87.png)

Once suspended it can be resumed with Resume button:

![](../../assets/user-guide-img/image88.png)

If a pipeline succeeds, all completed stages are painted in *Green*, indicating success.
The stages configured for failure scenario (red arrow) remain *Gray* as a Draft as they have not been executed.

![](../../assets/user-guide-img/image89.png)

If a pipeline fails, then the *Red* border indicates the failed stage:

![](../../assets/user-guide-img/image90.png)

A failed pipeline can be re-run with ![](../../assets/user-guide-img/image91.png) button from Pipelines overview page.

**Important**: *Job* stage has the *Logs* button ![](../../assets/user-guide-img/image50.png) for analyzing logs of a certain job.
Use the *History* button ![](../../assets/user-guide-img/image82.png) to view information about previous runs of the pipeline.
