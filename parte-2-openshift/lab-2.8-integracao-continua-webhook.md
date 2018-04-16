# 2.1.9 - Integração Contínua \(Webhook\)

Para que sempre que ocorra um commit o Openshift faça de forma automática o processo de build e deploy, iremos configurar  
um webhook, dessa forma o servidor git avisará o Openshift sempre que um commit novo ocorrer.

## Configuração webhook

Acesse a parte de builds.

![](../../extras/menu_261.png)

Depois selecione `workshop-ocp`

![](../../extras/selection_262.png)

Clique em `Configuration` e copie o link clicando no icone a direita

![](../../extras/selection_264.png)

No _Github.com_:

* Selecione `Settings` no menu horizontal

![](../../extras/selection_258.png)

* Selecione o `Webhooks` no menu lateral esquerdo 

![](../../extras/selection_259.png)

* Selecione `Add Webhooks`, cole a URL copiada no campo `Payload URL`, no campo `Content Type` selecione a opção `application/json`
* Clique em `Disable SSL verification`
* Finalize no botão `Add webhook`

![](../../extras/selection_088.png)

## Altere a aplicação

Para fazermos uma alteração na aplicação, vamos alterar a versão na página inicial da aplicação.

Clique no `Index.php`

![](../../extras/selection_265.png)

Depois clique no lapis para editar

![](../../extras/selection_266.png)

No `index.php` altere a linha com a versão da aplicação para versão 2.0.

![](../../extras/selection_268.png)

```text
echo "<h1>Openshift Workshop v2.0</h1>";
```

Clique em `Commit changes`

![](../../extras/selection_269.png)

Ou use a linha de comando do git para fazer essa alteraçao:

```bash
git add index.php
git commit -m "webhook adicionado"
git push
```

## Acompanhe o rolling deployment

Observe que não ocorre indisponibilidade durante o deployment
