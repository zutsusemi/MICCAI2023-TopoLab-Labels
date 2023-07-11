# TopoLab-Labels
The labels for the open-source dataset used in the paper "Topology-Preserving Automatic Labeling of Coronary Arteries via Anatomy-aware Connection Classifier"

## Description
The labels are stored in .json files, and each json has the following structure:
```
{
  l_points=[{point_set=[[...]], cls=c},...],
  r_points=[{point_set=[[...]], cls=c'},...],
  l_tree=[[x,y],...], 
  r_tree=[[x',y'],...]
}
```


*l_points*: A list containing centerline point coordinates and the vessel segment labels of l_tree. Each element of the list is a dictionary with 2 fields: point_set (all point coordinates of this segment) and cls (label of this segment).

*r_points*: A list containing centerline point coordinates and the vessel segment labels of r_tree. Each element of the list is a dictionary with 2 fields: point_set (all point coordinates of this segment) and cls (label of this segment).

*l_tree*: A list storing the structure of l_tree, each element [x, y] is an edge of the tree, where x is the x-th segment in l_points and y is the y-th segment in l_points.

*r_tree*: A list storing the structure of r_tree, each element [x, y] is an edge of the tree, where x is the x-th segment in r_points and y is the y-th segment in r_points.

## How to use
You need to first download the original orCaScore dataset.

Then, you need to align the label files with the images. The file name of the labels are the same as the corresponding images. Note that you probably need to reverse (and/or) swap the images' axis to align them. Before training your model, you should visualize the images and labels to ensure the alignment is correct.
