# Tensorflow.com Codelab

Fish recognition classifier

*Utilisation basique*

1) Ajouter deux dossiers 'data' & 'test' dans tf_files
2) Ajouter les dossiers 'classes', 'fish' et 'non-fish' dans 'data'
3) Remplir les trois dossier avec les datasets correspendant 
4) Lancer le script 'scripts/retrain.py' pour re-entrainer le model 
5) Lancer le script 'scripts/label_image.py' pour tester le model sur une image 


1) Paramètres (Indispensable) du scripts/retrain.py \
   --bottleneck_dir=tf_files/bottlenecks \
   --how_many_training_steps=500 --model_dir=tf_files/models/ \
   --summaries_dir=tf_files/training_summaries/"mobilenet_0.50_224" \
   --output_graph=tf_files/retrained_graph.pb \
   --output_labels=tf_files/retrained_labels.txt \
   --architecture mobilenet_0.50_224 \
   --image_dir=tf_files/data \

   Pour plus d'infos sur les params : python -m scripts.retrain -h

2) Paramètres (Recommandé) du scripts/label_image.py \
  --graph=/tmp/mobilenet_0.50_224.pb \
  --labels=/tmp/output_labels.txt \
  --image={Vos spec} \
  --input_layer=input \
  --output_layer=final_result \
  --input_mean={vos spec} \
  --input_std={vos spec} \
  --input_width={vos spec} \
  --input_height={vos spec} \

  Plus simple : python -m scripts.label_image --graph=tf_files/retrained_graph.pb --image=tf_files/data/test/maPhoto.jpg