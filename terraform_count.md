----## -Count Argument---

resource "aws_instance" "test_ec2" {
  ami = "ami-04a37924ffe27da53"
  instance_type = var.ins_typ
  vpc_security_group_ids = ["sg-022df83d202198a44","sg-07820c8c92ec1e426"] 
  count = 4 /* Will create a 4 AWS instance based on the value of count */
  tags = {
    Name = "Prod_servers"
  }
}
