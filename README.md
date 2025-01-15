<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação EasyPanel UNOAPI 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />

## Comando para Instalar EasyPanel

```bash
curl -sSL https://get.easypanel.io | sh
```

Adicione nome de Project

![48098522-0c485df00f5cadb0d329061c35fee46c](https://github.com/cwmkt/easypanelevotypebot/assets/91642837/b72c1359-91ca-4bf6-9fb1-32525ba5747b)

Clique na aba Templates

![48098535-90f9b4f370bb8b06cfd7e4acf0ee0f97](https://github.com/cwmkt/easypanelevotypebot/assets/91642837/03c1830c-621c-40b3-94ee-93eb568c8d2e)

Va ate final da pagina

![image](https://github.com/comunidadehubconnect/easypanelwoofedcrm/assets/91642837/828a9e88-45f2-4b6b-98f1-ab4f164d2889)

## Adicione código abaixo dentro do Schema 

![image](https://github.com/comunidadehubconnect/easypanelwoofedcrm/assets/91642837/74b97f33-e5d2-495d-aaba-25bb8b433adf)

## Lembre de alterar informações de Storage e adicionar Agente Criado Super_admin Chatwoot

```bash
{
  "services": [
    {
      "type": "app",
      "data": {
        "projectName": "tutoriais",
        "serviceName": "unoapi",
        "source": {
          "type": "image",
          "image": "clairton/unoapi-cloud:latest"
        },
        "env": "STORAGE_BUCKET_NAME=nomeseubucket \nSTORAGE_ACCESS_KEY_ID=IDSTORAGE \nSTORAGE_SECRET_ACCESS_KEY=KEYSTORAGE \nSTORAGE_REGION=REGIÃOSTORAGE \nSTORAGE_ENDPOINT=https://files3.urlstorage \nSTORAGE_FORCE_PATH_STYLE=true \nSTORAGE_TIMEOUT_MS=true \nBASE_URL=https://$(PRIMARY_DOMAIN) \nWEBHOOK_HEADER=Token Agente Criado Super_admin \nWEBHOOK_URL=https://urlchatwoot/webhooks/whatsapp \nWEBHOOK_TOKEN=Token Agente Criado Super_admin \nIGNORE_GROUP_MESSAGES=false \nIGNORE_BROADCAST_STATUSES=false \nIGNORE_BROADCAST_MESSAGES=false \nIGNORE_STATUS_MESSAGE=false \nIGNORE_OWN_MESSAGES=false \nUNOAPI_AUTH_TOKEN= \nREJECT_CALLS= \nREJECT_CALLS_WEBHOOK= \nSEND_CONNECTION_STATUS=false \nLOG_LEVEL=debug \nUNO_LOG_LEVEL=debug \nUNOAPI_RETRY_REQUEST_DELAY=1_000 \nAMQP_URL=amqp://admin:aub8i7KajdZOlQ98!@tutoriais_unoapi-rabbitmq:5672/default \nREDIS_URL=redis://default:aub8i7KajdZOlQ98!@tutoriais_unoapi-redis:6379",
        "deploy": {
          "replicas": 1,
          "command": null,
          "zeroDowntime": true
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "https": true,
            "port": 9876,
            "path": "/",
            "wildcard": false
          }
        ],
        "mounts": [
          {
            "type": "volume",
            "name": "unoapi_data",
            "mountPath": "/home/u/app"
          }
        ]
      }
    },
    {
      "type": "app",
      "data": {
        "projectName": "tutoriais",
        "serviceName": "unoapi-rabbitmq",
        "source": {
          "type": "image",
          "image": "rabbitmq"
        },
        "env": "RABBITMQ_ERLANG_COOKIE=h8uh8fuh8dfhdfhdfhf \nRABBITMQ_DEFAULT_VHOST=default \nRABBITMQ_DEFAULT_USER=admin \nRABBITMQ_DEFAULT_PASS=aub8i7KajdZOlQ98!",
        "deploy": {
          "replicas": 1,
          "command": null,
          "zeroDowntime": true
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "https": true,
            "port": 5672,
            "path": "/",
            "wildcard": false
          }
        ],
        "mounts": [
          {
            "type": "file",
            "content": "total_memory_available_override_value=512MB",
            "mountPath": "/etc/rabbitmq/rabbitmq.conf"
          }
        ]
      }
    },
    {
      "type": "redis",
      "data": {
        "projectName": "tutoriais",
        "serviceName": "unoapi-redis",
        "image": "redis:7",
        "password": "aub8i7KajdZOlQ98!"
      }
    }
  ]
}
```


### Pronto tudo Funcionando ✅😎

Creditos: `Bruno e Clairton`
