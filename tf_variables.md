**#tf-main_configuration file**

resource "aws_security_group" "sample_sg" {
  name = "Sample_sg"
  description = "For checking Variable function"
}

resource "aws_vpc_security_group_ingress_rule" "allow_traf" {
  security_group_id = aws_security_group.sample_sg.id
  cidr_ipv4 = var.vpn_ip
  from_port = var.ap_port
  ip_protocol = "tcp"
  to_port = var.ap_port
}

**#variable file**

variable "vpn_ip"{}
variable "ap_port"{}

**#*.tfvars file**

vpn_ip="100.30.20.45/32"
ap_port="8080"
