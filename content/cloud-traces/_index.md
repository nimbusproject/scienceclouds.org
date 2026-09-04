---
Title: Cloud Traces
ShowSummary: false
---
# Cloud Traces

Traces from existing parallel and distributed computing systems are a useful resource for researchers to replicate real-life workloads for their experiments. However, since cloud computing is a relatively new area few such traces are currently available.

## Using Chameleon Cloud Traces

We have developed a [trace data structure](cloud-trace-format) based on data from OpenStack Nova/Blazar/Ironic services, as well as [software](https://github.com/ChameleonCloud/starcompactor) to extract the appropriate data. We are making available data from the OpenStack cloud operated by the [Chameleon testbed](https://www.chameleoncloud.org/) for educational projects.

{{< trace-list >}}

We released Chameleon cloud traces to enable researchers to run their experiment and/or simulations with more realistic scientific testbed data. It would be a huge encouragement to us to see your works using our cloud traces. If you use our data in your research, it would be great to let us know. You can find our contact information [here](/contact).

For a quick start on downloading and using our cloud traces, we provided a [Jupyter Notebook example](https://github.com/ChameleonCloud/starcompactor/blob/master/ChameleonKVMCloudTraces.ipynb), which you can upload to [Chameleon Jupyter server](https://jupyter.chameleoncloud.org/). For more information about Chameleon Jupyter interface, please visit [Chameleon user documentation](https://chameleoncloud.readthedocs.io/en/latest/technical/jupyter.html).

## Sharing Your Cloud Traces

We also encourage research groups and cloud testbed providers to share their cloud traces with us. To share your cloud traces, please provide the following information with your cloud traces:

- Cloud trace format and format version
- How the cloud trace was generated (i.e. software tools)
- Cloud trace period
- Release date
- Contact information
- (Optional) Publications

If you are interested in sharing your cloud traces with us, please [contact us](/contact)!

- [ASP/LCRC](aps-lcrc/)

## Other Released Cloud Traces

The commercial cloud providers have released their cloud traces, and numerous researches had been done based on these released traces. We listed Microsoft Azure, Alibaba and Google release below for your reference.

- [Microsoft Azure VM traces](https://github.com/Azure/AzurePublicDataset)
- [Alibaba cluster data](https://github.com/alibaba/clusterdata)
- [Google cluster data](https://github.com/google/cluster-data)

