ssh -i ssh-key-location ec2-user@IP

sudo yum install java-17-amazon-corretto

java -version

sudo yum install maven -y

mvn -v

sudo yum install git -y

git clone https://github.com/shivam086r/Java-EC2-Newrelic-monitoring.git

cd Java-EC2-Newrelic-monitoring

mvn clean package

nohup java -jar target/my-java-app-1.0.0.jar &> /dev/null &
