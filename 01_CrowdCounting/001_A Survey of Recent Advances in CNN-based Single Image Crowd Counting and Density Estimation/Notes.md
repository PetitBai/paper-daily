# A Survey of Recent Advances in CNN-based Single Image Crowd Counting and Density Estimation



##  Definitions

* `Crowd Counting`: count the number of people in a crowd scene.
* `density estimation`: map an input crowd image to its corresponding density map which indicates the number of people per pixel present in the image.  

## Applications
* `Safety Monitoring`: video surveillance in places such as sports stadiums, tourist spots, shopping malls and airports. In such scenearios, apply tasks such as behavior analysis, congestion analysis, anomaly detection and event detection.
* `Disaster management`: crowd gatherings: sports events, music concerts, public demonstrations and political rallies; crowd related disasters: stampedes(life-threatening). used for early overcrowding detection and appropriate management of crowd.
* `Design of public spaces`: reveal important design shortcomings from **crwod safety and convenience point of view** for existing/designing public spots such as *airport terminals*, *train stations*, *shopping malls*, etc.
* `Intelligence gathering and analysis`:  For instance, in retail sector, crowd counting can be used to gauge people's interst in a product in a store(for appropriate product placement).
* `Virtual environments`: helps to establish mathematical models that can provide accurate simulations.
* `Forensic search`: helps to search for suspects and victims in events such as *bombing*, *shooting*, *accidents* in large gatherings, etc

## Techs & Tricks
* Detection-based approaches ; Regression-based approaches;  Density estimation - based approaches: CNNs lead the way
* In order to reduce false responses bg like buildings and trees in the images, training data is augmented with additional negative samples whose ground truth count is set as zero.
* It's common that the perfomance reduces drastically when applied to a new scene that is different from the training dataset.
* It looks like a fancy way to design multi workers corresponding to filters with receptive fields of different sizes(large, medium, small) and a decider to make choices.
* Patch-based training&evaluation results in loss of global context which is necessary for accurate estimation of count along with inefficiency during evaluation due to the use of a sliding window approche.

## Datasets
* UCSD: Single Park Scene
* Mall: Single Mall Scene
* UCF_CC_50: Extremely dense crowd, only 50 frames.
* WordExpo' 10 dataset: cross-scene: 1132 annotated video sequences captured by 108 surveillance cameras.
* Shanghai Tech dataset: Part A - 482 iamges randomly chosen from the Internet & Part B - images taken from the streets of metropolitan areas in Shanghai. a challenging dataset with diverse scene types and varying density levels. but still **too small**.
* mainstream loss: MAE & MSE

## Future research directions

Vision：CNN-Based deeper architectures will dominate further research in the field of crowd counting and density estimation.

* Collect large dataset (~CG-based synthetic datasets is a fancy way )

* Explore how to leverage from models trained on existing sources for new scenes. `Transfer learning` or `domain adaptation` may lead the way.
* Combine the techniques developed separately is a non-trivial work. Development for low-latency methods that can operate on real-time.
* Improve the quality of estimated crowd density map. maybe additional loss functions such as `adversarial loss` and `perceptual loss`. In principle, density estimation can be considered as an image-to-image translation problem.
* Design networks to incorporate additional contextual and scale information.