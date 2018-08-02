Simple Python Based Web application, to keep count of number of visits on our website.

Additionally with secrets. There are 2 ways to use secrets :
 1. Through ENV
 2. Through VolumeMounts
 
Have used both the ways. 

For creating a secret we have the secret.yml file. But since, it is just base64 encoded that might not be the ideal way to do the same.
1st way :
  Using the secret.yml file
  kubectl create -f secret.yml
2nd way is : 
  echo -n "root" > ./username.txt
  echo -n "password" > ./password.txt
  
  sh :- kubectl create secret generic db-user-pass --from-file=./username.txt --from-file=./password.txt
