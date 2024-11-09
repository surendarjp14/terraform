resource "aws_eip" "current" {
  domain = "vpc"

}

resource "aws_security_group" "allow_traffic" {
  name = "Allow traffic from Elastic IP"
}

resource "aws_vpc_security_group_ingress_rule" "allow_eip" {
  security_group_id = aws_security_group.allow_traffic.id
  cidr_ipv4 = "${aws_eip.current.public_ip}/32"
  from_port = 443
  ip_protocol = "tcp"
  to_port = 443
}
