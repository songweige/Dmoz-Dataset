# Dmoz-Dataset

* Since the old website of dmoz is down, the RDF dataset, i.e. the official download URL, became not available as well. Fortunately, an editor hosted one version of the dataset on its server. You can find it through this URL: https://curlz.org/dmoz_rdf/

* Note that the certification of the website is out-dated, so you need to add an exception to your browser. Then you can download the dataset.

* You can check this [blog](https://utatds.github.io/2017-01-18-URL-classification-using-DMOZ-data/) for the usage of this dataset for URL classification. Here are some shortcuts of the scripts used to process *content.rdf.u8*
```python
# extract the first 10000 line from the data
with open('content.rdf.u8', 'r') as fl_in:
    lines = [str(line) for line in fl_in[:10000]]
    
# extract titles, sescriptions, and topics
titles = [re.findall('<d:Title>(.+)</d:Title>', line) for line in lines]
descs = [re.findall('<d:Description>(.+)</d:Description>', line) for line in lines]
topics = [re.findall('<topic>(.+)</topic>', line) for line in lines]
```

Cheers!
