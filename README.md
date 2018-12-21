
# Pathology detection in chest X-ray
## New version https://gitlab.com/deflorator1980/cxr_patology_detection.git
## Usage (Chest X-rays in forlder radiographs)
```
python3 label_image.py 
```

## Train default
```
python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=CXR
```

## Train advanced
```
python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --learning_rate=0.001 \
  --how_many_training_steps=5000 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=/CXR
```

Library:
https://github.com/googlecodelabs/tensorflow-for-poets-2

Data set:
https://ceb.nlm.nih.gov/repositories/tuberculosis-chest-x-ray-image-data-sets/
