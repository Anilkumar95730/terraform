# TERRAFORM

 installation commands:
 
                         wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
                         echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg]
                         https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
                         sudo apt update && sudo apt install terraform
 
Vi main.tf


provider "aws" {

  region     = "ap-south-1"
  
  access_key = "AKIA"
  
  secret_key = "bcfA3"
  
}

resource "aws_instance" "one" {

  tags = {
  
  Name        = "terraform-instance"
    
  Environment = "dev"
    
  Project     = "amazon"
    
  }

  ami               = "ami-053b12d3152c0cc71"
  
  instance_type     = "t2.micro"
  
  key_name          = "pem0407"
  
  availability_zone = "ap-south-1b"
  
  count             = "2"
  
  root_block_device {
  
   volume_size = 10
    
  }
}

terraform fmt : it will changes the upper vi file inot correct format

terraform init : it will create the instance

terraform plan : it will excute and create yhe instance

terraform destroy : it will delete the instance


 
