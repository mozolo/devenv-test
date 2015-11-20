Vagrant.configure("2") do |config|
  config.vm.define "db" do |app|
    app.vm.provider "docker" do |d|
      d.image = "mongo:3.0"
      d.name = "db"
      d.ports = ["127.0.0.1:27017:27017"]
    end
  end
  config.vm.define "api" do |app|
    app.vm.provider "docker" do |d|
      d.image = "mozolo/3tier-api"
      d.name = "api"
      d.ports = ["127.0.0.1:5000:5000"]
      d.link "db:dblinkname"
    end
  end
end