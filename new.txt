provider "aws" {
    region = "us-east-1"
  
}
resource "aws_instance" "sample" {
    ami = "ami-08a52ddb321b32a8c"
    instance_type = "t2.micro"
    subnet_id = "subnet-036d83bfc74e674ac"
    security_groups =["sg-0132e4b6e77570d07"]
    key_name = aws_key_pair.test.id
    tags = {
      Name = "hosting"
    }

  
}
resource "aws_key_pair" "test" {
    key_name = "pair"
    public_key = "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDIPZzOo3iH7uWksd5qRt2tyMxVL+p9JHgjUukYj78xXfTU0ufHx7QdnuDBHl/sWoxQLEgnFnZMM4hv4hVyjxCu0b1cm4FFvlWGhEX0fexdtDvAHs6BkR7Wke5RUAqOWVfs2nfL7/tMP27AQAmxeOfa6wAdLu9TAMKIHzeRR/+HpuFybJ/vJdruCizFZfJHKbWl3N/2nAj7Vnj8l4Ix8GhV1LBItwT1HVxZc2fZISQVx1gvZ7O37s/hQfK/1htQxOTg0H1raMdoAzr/0rE/XO9qhvfSN8sJ9aEMEpMlJNB0ZHpNeHqTT/C23Dt7lvHGZyws653x2xzF/XH0QMH1C6/dZ7VxWUIiW1vY5M5k9vhJ1+gadrqGuC7+vYwUK58GXVZNDgvb/9lCdQBe9zgRUSJNAx8uV75tLp0zQtbbQft8MClcB7/dXJRjtJh34k49sEmObJ7avEEPIqS4PjOCFuQiQftcND36aIOhNtMjdC3004Pku4m96diQtAMrkBC9G0U= kotes@MSI"
  
}
