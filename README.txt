
# train default
python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=CXR

# train advanced
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

# usabe
python3 -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image=tbc1.jpg  

