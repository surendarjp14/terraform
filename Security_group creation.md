
resource "aws_security_group" "Fire_tls" {
  name        = "Fire_tls"
  description = "fIRE TLS inbound traffic and all outbound traffic"
    
}

resource "aws_vpc_security_group_ingress_rule" "Fire_tls_ipv4" {
  security_group_id = aws_security_group.Fire_tls.id
  cidr_ipv4         = "0.0.0.0/0"
  from_port         = 80
  ip_protocol       = "tcp"
  to_port           = 90
}

resource "aws_vpc_security_group_egress_rule" "allow_all_ipv4" {
  security_group_id = aws_security_group.Fire_tls.id
  cidr_ipv4         = "0.0.0.0/0"
  ip_protocol       = "-1"
  
}
