---
title: "&lt;transactionFlow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;transactionFlow&gt;
Especifica la compatibilidad de flujo de transacción para el enlace personalizado.  
  
## Sintaxis  
  
```  
  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|transactionProtocol|Especifica el protocolo de transacción que se va a utilizar.  Los valores válidos son los siguientes:<br /><br /> -   OleTransactions<br />-   WSAtomicTransactionOctober2004<br /><br /> El valor predeterminado es OleTransactions.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.  Para obtener más información sobre cómo utilizar este elemento de configuración, vea [Configuración de la transacción ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) y [Habilitar el flujo de transacciones](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de extremo a extremo, se puede perder el tiempo de espera de la transacción si el extremo de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.  Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>   
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Configuración de la transacción ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)   
 [Habilitar el flujo de transacciones](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)