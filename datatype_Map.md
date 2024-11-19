## ---MAP Datatype----


variable instc_tags{
  type = map
  default = {Name="App_server",Envn="Test",Location="Europe"}
}

output "Var_value" {
  value = var.instc_tags
}
