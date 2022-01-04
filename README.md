# HandWritten_Digit_Recognition
MNIST Handwritten Digit Recognition
---
<br><br>The MNIST dataset is an acronym that stands for the Modified National Institute of Standards and Technology dataset. It is a dataset of 60,000 small square 28×28 pixel grayscale images of handwritten single digits between 0 and 9. The task is to classify a given image of a handwritten digit into one of 10 classes representing integer values from 0 to 9, inclusively.<br>

---
---
<br><br>
Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive.
---
<b> #Results</b>
<br><br>
![image](https://user-images.githubusercontent.com/37467941/148041087-c1ffebe2-7ea4-4906-951c-189ca46119a3.png)

---
Model can saved by --> 
<br>model.save('Model.h5')<br>
The model can be loaded via the load_model() function.<br>
from tensorflow.keras.models import load_model<br>
# load and prepare the image<br>
from keras.preprocessing.image import img_to_array<br>
def load_image(filename):<br>
	# load the image<br>
	img = load_img(filename, grayscale=True, target_size=(28, 28))<br>
	# convert to array<br>
	img = img_to_array(img)<br>
	# reshape into a single sample with 1 channel<br>
	img = img.reshape(1, 28, 28, 1)<br>
	# prepare pixel data<br>
	img = img.astype('float32')<br>
	img = img / 255.0<br>
	return img<br>
 
# load an image and predict the class<br>
<br>
	img = load_image('Sample.png')<br>
	# load model<br>
	model = load_model('Model.h5')<br>
	# predict the class<br>
	predict_value = model.predict(img)<br>
	digit = argmax(predict_value)<br>
	print(digit)<br>
---

