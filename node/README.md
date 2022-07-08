## How to work on jenkins on ec2 server. Installation and configurations

### required for nodejs
``` sh curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash - ```

### install all pkgs in one command
```sh sudo apt install -y nodejs docker.io openjdk-8-jdk ```

### for Docker - required
```sh 
sudo usermod -aG docker $USER # current user must have a group call docker.
sudo chown $USER:docker /var/run/docker.sock # docker.sock file must have current user's onwership.
sudo chmod 666 /var/run/docker.sock # change the permission too. 
```

### for JAVA - optional
this is optional, but in case if you get a Java path error in Jenkins,
then you can use this method to resolve the issue.
find out java path using
readlink -f /usr/bin/javac | sed "s:/bin/javac::"
set JAVA_HOME path into .bashrc
```sh
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
PATH="$JAVA_HOME/bin:$PATH"
```
### finally
```sh
node --version
docker --version
java -version
```
