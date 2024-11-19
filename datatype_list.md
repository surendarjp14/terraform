##--List DataTYpe ----



resource "aws_instance" "tester_ec2" {
  ami = "ami-04a37924ffe27da53"
  instance_type = "t2.micro"
  vpc_security_group_ids = ["sg-022df83d202198a44","sg-07820c8c92ec1e426"] /* LIst datatype*/
}

variable "my-list" {
  type = list  ----- will store any value mentioned
}

variable "my-list" {
  type = list(number) -----will store only mentioned datatype in list
}

variable "user_name" {
  type = number---- will allow only numbers to be stored in this variable
}

resource aws_iam_user "username"{
  name = var.user_name
}

variable "my-list" {
  type = list(number)
}
