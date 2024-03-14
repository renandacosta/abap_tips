# Preenchimento do nome de usuário e TimeStamp na criação/alteração do registro:

Na CDS View Base adicionar a seguite anotação sobre o campo de usuário:

```abap
@Semantics.user.lastChangedBy: true  
```

Na CDS View Base adicionar a seguite anotação sobre o campo de TimeStamp:

```abap
@Semantics.systemDateTime.createdAt: true       
```    