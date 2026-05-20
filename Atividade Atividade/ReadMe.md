Olá!! Agora vou te ensinar como colocar o seu site para rodar na AWS

- Recomendo que vocÊ faça o seu arquivo em HTML no VS Code, pois fica mais fácil para você visualizar

# Hospedar na Amazon S3

- *Crie um Bucket*: Acesse o serviço S3 no console da AWS e crie um bucket. Desmarque a opção "Bloquear todo o acesso público" e marque a opção que está em um quadro amarelo.
- *Envie os arquivos*: Faça o upload de todos os arquivos do seu site para dentro desse bucket.

# Configurar permissões

- Vá na aba *Permissões* do seu bucket no S3.
- Em *Política do bucket*, clique em *Editar* e cole o código abaixo (lembre-se de substituir seu-nome-de-bucket pelo nome real do seu bucket):
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::seu-nome-de-bucket/*"
            ]
        }
    ]
}
```

# Habilitar Hospedagem de Site Estático:

- Ainda no seu bucket S3, vá na aba *Propriedades*.
- Role até o final e clique em Editar na opção "Hospedagem de site estático".
- Escolha Ativar, defina o documento de índice (geralmente index.html) e salve.

# Rodar o site:

- Após isso, marque o 🔳 do arquivo "index.html" e selecione a opção *Abrir*.

<img width="1904" height="946" alt="Captura de tela 2026-05-20 164823" src="https://github.com/user-attachments/assets/a35ebbbd-2817-42b6-b605-ad59b8ce650d" />

<img width="1905" height="944" alt="Captura de tela 2026-05-20 164847" src="https://github.com/user-attachments/assets/7c238ba3-f946-4f05-8366-64b3c59bce49" />
