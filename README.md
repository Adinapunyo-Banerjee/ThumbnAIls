# ThumbnAIls ▶️
ThumbnAIls is an AI-powered web app that analyzes various video and channel statistics to optimize YouTube video performance. 

# Training 🛠️
The code for training the deep learning model can be found here: https://www.kaggle.com/code/adinapunyobanerjee/youtube-likes-and-views-predictor

# The Model 🔥
So, the model takes in an image (the thumbnail to be predicted on) and the statistics of the video and channel.
To avoid huge training times, the Convolutional base was taken from the VGG16 pretrained model hence implementing Transfer learning techniques.
As usual, the convolutional base was left untrained (pre-trained) and the new dense layers trained.

Using tf.keras.utils.plot_model(), the model structure comes out to be:

![Model_graph](https://user-images.githubusercontent.com/110435416/225056423-4e6773c9-f185-4d15-8505-799d3bfb21ce.png)

Input statistics include Category ID of the video, Seconds since the channel was published,	Subscribers of the channel,	Total Videos the channel has,	Total Views the channel has and	Publishing date of the specific video.
The output is the Views and Likes predicted.

# Category ID ❔
The Youtube Search V3 API provides category IDs for different kinds of video content on Youtube. They are:

1	Film & Animation

2	Autos & Vehicles

10	Music

15	Pets & Animals

17	Sports

18	Short Movies

19	Travel & Events

20	Gaming

21	Videoblogging

22	People & Blogs

23	Comedy

24	Entertainment

25	News & Politics

26	Howto & Style

27	Education

28	Science & Technology

29	Nonprofits & Activism

30	Movies

31	Anime/Animation

32	Action/Adventure

33	Classics

34	Comedy

35	Documentary

36	Drama

37	Family

38	Foreign

39	Horror

40	Sci-Fi/Fantasy

41	Thriller

42	Shorts

43	Shows

44	Trailers

# Preprocessing ⚙️
SKLearn's Standard Scaler has been used to preprocess the input. Their pickle dump file can be found in the `Scalers and Model` folder.
Simple image normalization has been used to get image pixel values between the range of 0 to 1.
Images were also resized to `150*150` resolution before training.

# Dataset 📊
The dataset used can be found here: https://www.kaggle.com/datasets/adinapunyobanerjee/youtube-thumbnail-dataset

Data was collected using the Youtube Search V3 API, and channel names were taken from the 'Top 100 channel most subscribed' list from each category from Socialblade.

