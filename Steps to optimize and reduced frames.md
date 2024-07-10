Real Time Video Optimization ![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.001.png)![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.002.png)

Steps to optimize and reduced frames:-  

1)-Give the path of video **video\_path='1.mp4'** to calculate its original size and optimise it. 2)-Create the   database of known or  verified person in the testing video  and upload it. 

3)-In first  stage set the threshold according to requirements for removing similar frames in the video which is working on cosine similarity (set threshold>=0.98). 

4)-Now !git clone "**https://github.com/kb22/Create-Face-Data-from-Images**" the following directory to acess face extraction model. 

5)-Now load the path of Caffemodel from the loaded github repo 

`     `caffemodel\_path = '/content/Create-Face-Data-from- Images/model\_data/weights.caffemodel'![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.003.png) 

and also load the path of architecture for to make  caffemodel  workable. 

prototxt\_path = '/content/Create-Face-Data-from- Images/model\_data/deploy.prototxt'![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.004.png) 

6)-Make new directory names "faces" to store the images of extracted face from every frames 

7)-Now install the package deepface package . 

8)-Now git cone the repo for  deepface to get  its all  requirements  

! git clone "https://github.com/serengil/deepface.git" ![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.005.png)!pip install -e 

9)-From deepface repo package import Deepface function 

10)-Download the file haarcascade\_fullbody.xml that uses haarcascade model for identification of            Humans. 

11)-Combining all iterate over each frames of the video that stored as numpy array and extract faces    from frames and stored it in directory name Faces that we created earlier. 

12)-Use Deepface.find() function to compare the extracted faces with the datatbase to check  wheather it is verified or not. 

result=DeepFace.find(img\_path = 'extracted\_img \_path.jpeg',db\_path =![](Aspose.Words.498dc4eb-d698-45fc-bbe5-dec25f33951a.006.png)"database\_path",enforce\_detection = False) 

13)-Declare video writter with fourcc "mp4" to store the optimised video. 

**Testing video:** 

`             `Original video size = 1.85 MB (video consist of 3 person)              Case-1-  Database carrying 1 verified person 

`                             `Final video size = 1.26 MB 

`             `Case-2- Database carrying 2 verified person 

`                             `Final video size = 0.35 MB 
