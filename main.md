provider "aws" {
    region = "us-east-2"
    profile = "default"
}

module "sg" {
   source = "./sg"
}

module "ec2-web" {
   source = "./ec2"
   sg_id = module.sg.sg_id
}

module "ec2-app" {
   source = "./ec2"
   sg_id = module.sg.sg_id
}






