# videos-transfer-vimeo
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/aws-samples/videos-transfer-vimeo/edit/main/README.md)

Este projeto demonstra como transferir vídeos de uma conta Vimeo para um bucket do Amazon S3.

## Pré-requisitos

- [Python 3](https://www.python.org/downloads/), instalado
- Uma conta [Vimeo](https://vimeo.com/) com plano Standard ou maior
- Um bucket no Amazon S3
## Passo-a-passo

1. Instale as bibliotecas necessárias utilizando o [pip](https://pypi.org/project/pip/): ``` pip install -r requirements.txt ``` ou ``` pip3 install -r requirements.txt```
2. No mesmo diretório do script python, crie um arquivo chamado ```.env```, com o formato a seguir, e preencha os campos necessários:
  ``` 
  AWS_ACCESS_KEY = ''
  AWS_SECRET_ACCESS_KEY = ''
  BUCKET_NAME = ''
  VIMEO_CLIENT_IDENTIFIER = ''
  VIMEO_TOKEN = ''
  VIMEO_CLIENT_SECRET =   ''
  OPTIONAL_PATH = ''
```
- ```AWS_ACCESS_KEY``` e ```AWS_SECRET_ACCESS_KEY```: as chaves pública e privada, respectivamente, de um usuário com permissões sobre o bucket em questão
  - A [permissão](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_id-based) necessária é ```s3:PutObject``` sobre o bucket (```arn:aws:s3:::<bucket-name>/*```)
- ```BUCKET_NAME```: o nome do bucket
- ```VIMEO_CLIENT_IDENTIFIER```:
  - Acesse [https://developer.vimeo.com/apps](https://developer.vimeo.com/apps)
  - Crie um App, preenchendo seu nome e descrição
  - Insira na variável o valor em ```Client identifier```
- ```VIMEO_TOKEN``` e ```VIMEO_CLIENT_SECRET```:
  - Na mesma página, em ```Authentication```, selecione o campo ```Authenticated (you)```
  - Selecione os escopos ```Public```, ```Private``` e ```Video Files```
  - Clique em ```Generate```
  - Na aba ```Personal Access Tokens```, copie o valor em ```Token``` para a variável ```VIMEO_TOKEN```
  - Na aba ```Manage App Secrets```, copie o valor em ```Client secrets``` para a variável ```VIMEO_CLIENT_SECRET```
- ```OPTIONAL_PATH```: caso deseje transferir os vídeos para um caminho específico dentro do bucket, coloque o caminho nessa variável **SEM** as primeira e última ```/``` 
  - Por exemplo: se os vídeos devem ser armazenados em ```/videos/projeto/janeiro/```, o valor em ```OPTIONAL_PATH``` deve ser ```videos/projeto/janeiro```
  
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.
