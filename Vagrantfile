Vagrant.configure('2') do |config|
    config.vm.box = 'azure'

    config.vm.provider :azure do |azure|

        azure.mgmt_certificate = 'certificate.pem'
        azure.mgmt_endpoint = 'https://management.core.windows.net'
        azure.subscription_id = 'subscription0d

        azure.vm_image = 'b39f27a8b8c64d52b05eac6a62ebad85__Ubuntu-14_04_1-LTS-amd64-server-20150123-en-us-30GB'
        azure.vm_user = 'user'
        azure.vm_password = 'pass'

        azure.vm_name = 'ubuntu-test' 
        azure.vm_location = 'West Europe'

      	azure.ssh_port = '22'

    end

$script = <<SCRIPT

sudo apt-key adv --keyserver pgp.mit.edu --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
sudo apt-get update
sudo apt-get -y install curl unzip git-core mono-devel

mozroots --import --sync
curl https://raw.githubusercontent.com/aspnet/Home/master/kvminstall.sh | sh && source ~/.kre/kvm/kvm.sh && kvm upgrade

git clone https://github.com/davidfowl/HelloWorldVNext ~/helloworld
sed -i s/aspnetvnext/aspnetmaster/g ~/helloworld/NuGet.Config
cd ~/helloworld

SCRIPT

    config.vm.provision "shell", inline: $script, privileged: false
    config.ssh.username = 'username'
    config.ssh.password = 'password'
end