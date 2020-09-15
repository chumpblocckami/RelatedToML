# RelatedToML: Random things i code

## MY RETRIVER

![](https://cdn.cardsrealm.com/images/cartas/crop/mb1-mystery-booster/myr-retriever-1613-med.jpeg?263) 

Class for Image (maybe document?) Retrival. 
Documentation will be exploided soon.

Build with face retrival in mind.

Essentialy it uses a pretrained model for gain access to neural feature, and then it construct a KDTree on cluster of datapoint for fast retrival.

Usage:
```
myr = MyRetriver()
myr.select_model("vggface") #other can be used

path = path_to_file
if ("MYR_features.pkl" in os.listdir(path_to_file)):
  print("Load files...")
  myr.load_data_from_file(path_to_file)
else:
  print("Init")
  myr.load_data(path,only_faces=True)
  myr.save_data_to_file(path_to_file)

myr.getCentroids(feature_selection=False) #get centroids for fast indexing

myr.getRetrieval(new_image,cropped=False)
```

Also there are some pretty viz:
```
myr.getViz("centroids")
myr.getViz("images")
```
