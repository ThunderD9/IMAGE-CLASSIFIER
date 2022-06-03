First I tried using 128 filters and 2x2 kernel for the convolution layer
[tf.keras.layers.Conv2D(
            128, (2,2), activation="relu", input_shape=(IMG_WIDTH, IMG_HEIGHT, 3)
        )]
         and with Max pooling (2, 2)
         [tf.keras.layers.MaxPooling2D(pool_size=(2, 2)),
        tf.keras.layers.Conv2D(
            128, (2, 2), activation="relu", input_shape=(IMG_WIDTH, IMG_HEIGHT, 3)
        ]
        and a hidden layer with droupout 0.5 and 128 units, and also with another (2, 2) maxpooling layer
        and I got an Accuracy of 92.74% and loss of 2.52%
        Then I Changed the second convolution layer to 32, (2, 2), activation="relu", after that i got an accuracy of 80.83% and a loss of 6.3%.
        Then I changed both the convolution layer to 32, (3, 3) and I got an Accuracy of 94.33% and loss of 2.24%***The best one***
        Then I  changed both max pooling layers to (4,4) and I got an Accuracy of 43.52% and loss of 17.02% (compilation time decreased)
        Then I changed back both the max pooling layers to (2, 2) and increased the both the convolution layers to 128(3, 3) and I got an Accuracy of 5.44% and loss of 34.98% (compilation time increased)
        Then I changed the first convolution layer to 32, (3, 3) and the 2nd to 64, (3,3) and got an Accuracy of 98.02% and loss of 0.791%

        Also I changed the dropout rate and found that 0.5 is good enough compared to other values. I found that having two 32,(3, 3) is optimal.