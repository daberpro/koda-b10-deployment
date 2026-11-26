# Initial Setup
```sh 
sudo adduser koda && sudo adduser dako 
sudo addgroup devteam
sudo usermod -aG devteam koda 
sudo usermod -aG devteam dako 
```
result initialize 

![](img/image.png)

# 2. Make koda owner dand group owner devteam of projectX
```sh
# because i already on srv 
sudo mkdir projectX
sudo chown koda:devteam projectX 
```
![](img/image_1.png)

# 3. Restricting Access
```sh
sudo chmod 750  projectX
```
![alt text](img/image-2.png)

# 4. As user koda create following structure
![alt text](img/image-3.png)
```sh
su koda
cd projectX/
touch README.md
mkdir src && touch src/app.sh
mkdir data && touch data/input.txt
```
![alt text](img/image-4.png)

# 5. Fixing permission
```sh
sudo chmod ug+x,o-x app.sh
```
![alt text](img/image-5.png)

# 6. Protecting sensitive data
```
sudo chmod 600 input.txt 
```
![alt text](img/image-6.png)

# 7. Allow group collaboration
```sh
# change ownerhsip of src because from step
# 4 - 6 the src was own by groups koda
sudo chown :devteam src
sudo chmod -R 775 src
```
![alt text](img/image-8.png)

# 8. Change ownership
```sh
sudo chown -R koda:devteam projectX/ 
```
![alt text](img/image-9.png)

# 9. Prevent Accidental Deletion
```sh
sudo chmod 774 projectX
```
![alt text](img/image-10.png)

# 10. Make readme readonly
```sh
sudo chmod 744 README.md 
```
![alt text](img/image-11.png)

# 11. Resignation and project handover
```sh
sudo chown dako -R projectX/
```
![alt text](img/image-12.png)

