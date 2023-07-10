# videos-transfer-vimeo
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/aws-samples/videos-transfer-vimeo/edit/main/README.md)

Este projeto demonstra como transferir vídeos de uma conta Vimeo para um bucket do Amazon S3.

## Pré-requisitos

- [Python 3](https://www.python.org/downloads/), instalado
- Uma conta [Vimeo](https://vimeo.com/) com plano Standard ou maior
- Um bucket no Amazon S3
- 
## Passo-a-passo

1. Instale as bibliotecas necessárias utilizando o [pip](https://pypi.org/project/pip/): ``` pip install boto3 requests dotenv vimeo ```
2. No mesmo diretório do script python, crie um arquivo chamado ```.env```, com o formato:
  ``` 
  AWS_ACCESS_KEY = ''
  AWS_SECRET_ACCESS_KEY = ''
  BUCKET_NAME = ''
  VIMEO_CLIENT_IDENTIFIER = ''
  VIMEO_TOKEN = ''
  VIMEO_CLIENT_SECRET =   ''
  OPTIONAL_PATH = ''
```
- ```AWS_ACCESS_KEY``` e ```AWS_SECRET_ACCESS_KEY```: são as chaves pública e privada, respectivamente, de um usuário com permissões sobre o bucket em questão. A [permissão](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_id-based) necessária é ```s3:PutObject``` sobre o bucket (```arn:aws:s3:::<bucket-name>/*```) 
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.
