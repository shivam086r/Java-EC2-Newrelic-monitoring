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

################ uninstalling new-relic ################

ps aux | grep newrelic

sudo find / -name "*newrelic*" 2>/dev/null

sudo yum remove newrelic-infra -y


sudo rm -rf /etc/yum.repos.d/newrelic-infra.repo
sudo rm -rf /etc/newrelic-infra.yml
sudo rm -rf /etc/newrelic-infra
sudo rm -rf /var/cache/dnf/newrelic-infra*
sudo rm -rf /var/db/newrelic-infra
sudo rm -rf /opt/newrelic-infra
sudo rm -f /usr/local/bin/newrelic
sudo rm -rf /root/.newrelic

sudo systemctl daemon-reload

find / -name "*newrelic*" 2>/dev/null


######################### Installing newrelic agent manually for java app only ######################





