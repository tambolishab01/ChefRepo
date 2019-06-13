
######update repo#####

execute "update-upgrade" do
  command "sudo apt-get update && sudo apt-get upgrade -y"
  action :run
end

#####installing java pckg ###########

package "openjdk-8-jdk" do
   action :install
   options '--force-yes'
end

#######instaling apache ###########

package "apache2"

service "apache2" do
        action [:start, :enable]
end

#########creating directory for jenkins war file download location##

directory '/chef-jk' do
  mode '0755'
  action :create
end

#######Downloading Jenkins ###########

bash 'installjkwarfile' do
   cwd '/chef-jk'
   code <<-EOH
   wget http://mirrors.jenkins.io/war-stable/2.89.4/jenkins.war
  EOH
end

##############installing Jenkins using Jar tool ###########

bash 'installjk' do
  cwd '/chef-jk'
  code <<-EOH
  cd /chef-jk
  java -jar jenkins.war --httpPort=8090
EOH
end



====================================
bash 'install' do
  cwd '/chef-jk'
  code <<-EOH
 java -jar -httpPort=9999 jenkins.war

EOH
end

command to unrwap war

jar -xcf filename.war


