# CDS View com ajuda de pesquisa para valores fixos de domínio:

Primeiro, deve-se cria uma CDS View que consuma a CDS View standard `I_DomainFixedValueText`.
Adicionar na cláusula `WHERE` o nome do domínio que se deseja filtrar:

```abap
@AbapCatalog.viewEnhancementCategory: [#NONE]
@AccessControl.authorizationCheck: #NOT_REQUIRED
@EndUserText.label: 'Depósito Padrão - Status'
@Search.searchable: true
@ObjectModel.dataCategory: #VALUE_HELP
@ObjectModel.usageType:{
    serviceQuality: #X,
    sizeCategory: #S,
    dataClass: #MIXED
}
define view entity ZVH_DEPOSITOPADRAO_STATUS
  as select from I_DomainFixedValueText
{

      @Search.fuzzinessThreshold: 0.8
      @Search.defaultSearchElement: true
      @EndUserText.label: 'Status'
  key DomainValue as Status,

      @Search.fuzzinessThreshold: 0.8
      @Search.defaultSearchElement: true
      @EndUserText.label: 'Descrição'
      DomainText as Descricao

}
where  SAPDataDictionaryDomain = 'ZSTATUS' 
```

Em seguida adicionar no campo que receberá a ajuda de pesquisa a anotação abaixo:

```abap
@Consumption.valueHelpDefinition: [{
       entity: {         name: 'ZVH_DEPOSITOPADRAO_STATUS',
                          element: 'Status'},
    useForValidation: true }
    ]         
```    