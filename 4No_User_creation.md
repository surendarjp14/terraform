variable "user_list"{
type = list
default = ["SurenJ","Rootuser","Architect","Nayagan"]
}
resource "aws_iam_user" "Prod_server_access" {
  name = var.user_list[count.index]
  count = 4
}
