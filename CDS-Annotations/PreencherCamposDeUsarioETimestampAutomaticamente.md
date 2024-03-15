# Preenchimento do nome de usuário e TimeStamp na criação/alteração do registro:

Na CDS View Base adicionar a seguite anotação no campo de usuário de criação:

```ABAP CDS
 @Semantics.user.createdBy: true   
```
Na CDS View Base adicionar a seguite anotação no campo de usuário de modificação:

```ABAP CDS
@Semantics.user.lastChangedBy: true    
```

Na CDS View Base adicionar a seguite anotação sobre o campo de TimeStamp de criação:

```ABAP CDS
@Semantics.systemDateTime.createdAt: true       
```  

Na CDS View Base adicionar a seguite anotação sobre o campo de TimeStamp de modificação:

```ABAP CDS
@Semantics.systemDateTime.lastChangedAt: true   
``` 