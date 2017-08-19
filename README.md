# autoencoder_example

Disclaimer: This is not an official Google product.

## Setup

### Launch Cloud Datalab from Cloud Shell terminal.
```
$ datalab start mydatalab
```

### Open a new notebook on Datalab

### Run the following code in the first command cell.
```
%%bash
pip install --upgrade tensorflow
git clone https://github.com/enakai00/autoencoder_example
cd autoencoder_example
PROJECT_ID=$(gcloud config list project --format "value(core.project)")
BUCKET="gs://${PROJECT_ID}-mnist"
gsutil mkdir $BUCKET
./scripts/create_records.py
gsutil cp /tmp/data/train.tfrecords ${BUCKET}/data/
gsutil cp /tmp/data/test.tfrecords ${BUCKET}/data/
```

This will take a few minutes. Please be patient.

### Go back to the notebook list and open the example notebook.
`autoencoder_example/AutoEncoderExample.ipynb`
