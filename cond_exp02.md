
resource "aws_instance" "test_ec2" {
  ami = "ami-04a37924ffe27da53"
  instance_type = var.instance == "prod" && region == "ap-south-1" ? t2.large : t2.micro
  vpc_security_group_ids = ["sg-022df83d202198a44","sg-07820c8c92ec1e426"] 
  tags = {
    Name = "Prod_servers"
  }
