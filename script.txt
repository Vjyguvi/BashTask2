
#! /bin/bash


# update

sudo yum update -y > /dev/null

which git > /dev/null

exit=$? > /dev/null

if [ $exit -eq 0 ]; then

        echo "git already installed"

else
        sudo yum install git -y > /dev/null
fi

which httpd > /dev/null

exit1=$?

if [ $exit1 -eq 0 ]; then

        echo "httpd already installed"

else
        sudo yum install httpd -y > /dev/null
fi

sudo systemctl start httpd

sudo echo "<body> Hi Guvi .. I am Vijay .. Thanks .. </body> " > /var/www/html/index.html

sudo systemctl start httpd
echo " Web server installed. Please open port 80 to access "
