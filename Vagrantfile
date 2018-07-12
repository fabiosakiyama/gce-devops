$GOOGLE_PROJECT_ID = "gce-devops"
$GOOGLE_CLIENT_EMAIL = "fabiosakiyama@gmail.com"
$GOOGLE_JSON_KEY_LOCATION = "/home/fabiosak/Dev/Vagrant/gce-devops/GCE-DEVOPS-6c2a20b6f0cd.json"
$LOCAL_USER = "fabiosak"
$LOCAL_SSH_KEY = "~/.ssh/id_rsa"

Vagrant.configure("2") do |config|
  config.vm.box = "google/gce"

  config.vm.define :jenkins do |jenkins|
    jenkins.vm.provider :google do |google, override|
      google.google_project_id = $GOOGLE_PROJECT_ID
      google.google_client_email = $GOOGLE_CLIENT_EMAIL
      google.google_json_key_location = $GOOGLE_JSON_KEY_LOCATION
      google.zone = "us-central1-c"

      override.ssh.username = $LOCAL_USER
      override.ssh.private_key_path = $LOCAL_SSH_KEY
      
      google.zone_config "us-central1-c" do |jenkins_zone|
        jenkins_zone.name = "jenkins"
        jenkins_zone.image = "centos-7-v20180611"
        jenkins_zone.machine_type = "n1-standard-1"
        jenkins_zone.zone = "us-central1-c"
        jenkins_zone.metadata = {"zone" => "US Central 1c"}
      end
    end
  end

  config.vm.define :dockerhub do |dockerhub|
    dockerhub.vm.provider :google do |google, override|
      google.google_project_id = $GOOGLE_PROJECT_ID
      google.google_client_email = $GOOGLE_CLIENT_EMAIL
      google.google_json_key_location = $GOOGLE_JSON_KEY_LOCATION
      google.zone = "us-central1-c"

      override.ssh.username = $LOCAL_USER
      override.ssh.private_key_path = $LOCAL_SSH_KEY

      google.zone_config "us-central1-c" do |dockerhub_zone|
        dockerhub_zone.name = "dockerhub"
        dockerhub_zone.image = "centos-7-v20180611"
        dockerhub_zone.machine_type = "n1-standard-1"
        dockerhub_zone.zone = "us-central1-c"
        dockerhub_zone.metadata = {"zone" => "US Central 1c"}
      end
    end
  end

end
