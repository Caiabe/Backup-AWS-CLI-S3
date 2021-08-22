# Backup-AWS-CLI-S3
● Configurar Bucket para receber Backup do SQL (Copiar ARN)

● Criar política e regra EC2, com acesso ao bucket

● Atachar a regra no EC2

● Acessar e instalar AWS CLI na Instancia

	apt install snapd
	sudo snap install aws-cli --classic

● Criar arquivo para fazer upload do backup do banco

# Sync AWS
● Criar arquivo upload-sql_aws.sh, dar permissão de execução e adicionar a seguinte linha:

● (comando | atributo (sync) | origem | destino)

aws s3 sync /home/ubuntu/sql/dump s3://veloxcloud-bkp

# Crontab

● (minuto | hora)

00 20 * * *     root /root/upload_sql_aws.sh

00 05 * * *     root rm -fr /home/ubuntu/sql/dump/*


