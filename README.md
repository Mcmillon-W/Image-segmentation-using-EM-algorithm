# Image-segmentation-using-EM-algorithm
Open google colab in browser and open the relevant notebook.

Upload the 3 images present in the Input Folder to the notebook.
(Option is present in the left panel of the screen)

The 3*4 image matrix is present in the last console just before the last cell.
You will have to scroll down passed all the iterative statements present in the console.

Output Folder has saved each intermediate steps( each iterative step) for each segement and for each image.
Some will not have 20 images as they have converged before 20 iterations. (0.png is the initial original image)



These results are also written in the last cell of the notebook in the form of a comment. Which reflect on the results obtained as well as my understanding of EM algorithm.

Water coins : The image is segemented. It distinguishes mainly between the 2 features 1.Coins 2.Water .The algorithm works best with 2 segments as there are
                only 2 components to the image. The red cluster defines the coins and the blue cluster defines the water present in the image. This is ideal as if we were to ask a human 
		how many things/components are present in the image, he too will say coins and water.

Jump : The image is best segmented when we define 4 clusters.   1.Red cluster - Human  
								2.blue cluster - Mountain 
								3. Yellow cluster - Troposphere 
								4. Pink cluster  - Stratosphere. 
This is just about how a human would describe the image if not just saying it in layman terms that there are 3 things present in the picture - person,mountain,
sky(comprises of both stratosphere and troposphere).

Tiger : We get an optimal result when we choose 5 segments.However it could be be better if we choose more number of segments.For example The distribution of orange pixels is wide spread
(larger pi/deviation) leading to, sand(light orange color) and the tiger (dark orange color) being under the same cluster.Pink cluster - Tiger and sand    
															Yellow cluster -black regions of the image(like shadow,stripes)   
															Blue cluster - Whitish colored regions   
															Red cluster-Blue regions of the image(water)     
															Green cluster - Green regions(Grass patch)

I have gained an understanding of how the EM algorithm and Kmeans works. As the iterations the algorithm goes through increases, the mean(mu) and standard deviation(sigma/pi) of the segment
/cluster converges to the actual segment/cluster. We get closer to the actual mixture of distributions (of the pixel intensities) present in the image.
However we will have to give a decent guess of mu and pi. Here it is taken as 1/(no. of segments) (plus some noise is added). Not only that we will also have to tell the algorithm of how
many segments/clusters are present in the image beforehand for an optimal result. As we can see for certain images, with certain pre-defined no. of segments. mu and pi converge in 
iterations less than 20(max no. of iterations).
Of course will we also require sufficient no. of iteration to get the distributions which has highest chance of producing the relevant point.  
