## Resolving issues and error in dependencies like:
Note: I used Ubuntu 14.04 LTS Server. 

> easydict

if not able to install using pip or conda, lets make it from source code.

```python
git clone git@github.com:livoras/easydict.git
cd easydist
sudo python setup.py install
```
> OpenCV
 Again, this didn't work for me and so I had to install from source and compile. Here you go with steps.
 
````
git clone https://github.com/khemanta/Install-OpenCV.git
cd Install-OpenCV
cd Ubuntu
chmod +x *
./opencv_latest.sh
 ```
>- check if the installation is complete with final line.

```
# it will take some time to install
# logs truncated from above
-- Installing: /usr/local/share/OpenCV/samples/python2/demo.py
-- Installing: /usr/local/share/OpenCV/samples/python2/morphology.py
-- Installing: /usr/local/share/OpenCV/samples/python2/grabcut.py
-- Installing: /usr/local/share/OpenCV/samples/python2/distrans.py
-- Installing: /usr/local/share/OpenCV/samples/python2/gaussian_mix.py
-- Installing: /usr/local/share/OpenCV/samples/python2/opt_flow.py
OpenCV 2.4.13 ready to be used
````
>- conforming installation and import environment correctly

```python
python -c "from cv2.cv import *"
```
If it throws error... try the following...

```python
python -c "import sys; sys.path.append('/usr/local/lib/python2.7/site-packages'); import cv2"
```
If above works we need to set path variable to import site-packages. The python directory may be different based on your python version like 2.5 or 2.6 or 2.7 etc so will be the name as per in path to be included.

Following would be hepful

```
python --version
which python
```

To import opencv/cv2 in python environment either (a.) append the following code or (b.) add the path in your ~./bashrc

>- Option-(a.) appending the following line your code
```python
import sys
sys.path.append('/usr/local/lib/python2.7/site-packages')
```

>- Option-(b.) This could be permanent and easier solution.
```
vim ~/.bashrc
# Added manually for openCV as site packages not including
export PYTHON_LOCAL="$PYTHONPATH:/usr/local/lib/python2.7/site-packages/"
```







  
