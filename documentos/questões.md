A gestão de quantidades dos produtos é feita pelo sistema B, que alimenta o canal Web. A validade dos produtos está no sistema A, que alimenta o canal client/server. No canal Web é possível adquirir um produto que já venceu? No canal Client/server é possível adquirir um produto que não tem estoque?

O Sistema A é tecnologicamente mais recente e alimenta o canal Client/server, que possui telas e campos fixos. O sistema B, mais antigo, alimenta o canal Web, onde os produtos possuem telas e campos personalizados. Não parece incoerente?

Há alternativas para um sistema mainframe atualmente, como por exemplo os produtos da AWS. Valeria a pena propor uma mudança, que acredito que seria bastante estrutural? Ou vamos partir do pressuposto que o mainframe vai continuar existindo?

Os dois canais, quando se trata de contratação ou cancelamento de um plano, passam pelo sistema B que consulta o sistema A com intermédio da websphere. O sistema A armazena o cadastro dos clientes, porém só é atualizado uma vez por dia (rotina diária do control+M). Digamos que, por exemplo, um cliente adquire um produto (B -> C -> A -> C -> B), isso fica armazenado em B. Diagamos que antes de essa informação alimentar o banco de dados em A, o cliente resolva cancelar esse produto. Na consulta para validação do processo, A ainda não terá a informação de que o cliente adquiriu o produto. Como resolver isso? Armazenar as informações de cadastro de cliente em B? Atualizar os dados de B assim que é feita a consulta?

Qual a razão do sistema A existir? Qual a importância dele?


