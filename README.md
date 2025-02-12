############ App-deployment ###########################

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

############### New-relic-commands ################################

curl -Ls https://download.newrelic.com/install/newrelic-cli/scripts/install.sh | bash && sudo NEW_RELIC_API_KEY=<API-KEY> NEW_RELIC_ACCOUNT_ID=6437367 /usr/local/bin/newrelic instal

newrelic

sudo systemctl status newrelic-infra

sudo systemctl stop newrelic-infra
sudo systemctl disable newrelic-infra
sudo yum remove newrelic-infra -y

################ Disable Logs Forwarding ################

sudo vim /opt/newrelic/newrelic.yml


