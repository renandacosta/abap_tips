# Preenchimento do nome de usuário e TimeStamp na criação/alteração do registro:

Na CDS View Base adicionar a seguite anotação no campo de usuário de criação:

```abap
 @Semantics.user.createdBy: true   
```
Na CDS View Base adicionar a seguite anotação no campo de usuário de modificação:

```abap
@Semantics.user.lastChangedBy: true    
```

Na CDS View Base adicionar a seguite anotação sobre o campo de TimeStamp de criação:

```abap
@Semantics.systemDateTime.createdAt: true       
```  

Na CDS View Base adicionar a seguite anotação sobre o campo de TimeStamp de modificação:

```abap
@Semantics.systemDateTime.lastChangedAt: true   
``` 