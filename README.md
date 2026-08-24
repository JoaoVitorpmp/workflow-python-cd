1. O que representa a etapa de CI neste projeto?
A etapa de CI (Continuous Integration / Integração Contínua) representa a fase automatizada responsável por preparar o ambiente, instalar as dependências do projeto e executar os testes unitários (`pytest -v`) sempre que há um `push` ou `pull_request` para a branch `main`. O objetivo é garantir que o código novo integrou-se corretamente com o restante do projeto sem quebrar as funcionalidades existentes.

2. O que impede a execução do Continuous Delivery quando existe um defeito?
O gatilho `needs: ci` configurado na etapa de Continuous Delivery. Como a entrega depende diretamente do sucesso do job de CI, se houver qualquer falha (como um teste quebrado no `pytest`), o job de CI falhará e a etapa de Delivery será automaticamente cancelada ou ignorada, impedindo que o artefato com defeito seja empacotado e publicado.

3. Qual seria a próxima etapa necessária para transformar este pipeline em Continuous Deployment?
A próxima etapa seria adicionar um job subsequente (por exemplo, `deploy`) configurado para rodar após o `delivery` e integrar uma ferramenta ou script de publicação automática (como enviar para o PyPI, fazer o deploy em um servidor de produção ou container registry), substituindo ou complementando a simples criação e upload do artefato por um processo que coloque a aplicação diretamente em ambiente produtivo sem intervenção manual.


https://github.com/JoaoVitorpmp/workflow-python-cd/actions/runs/32790991313/artifacts/9543115054
