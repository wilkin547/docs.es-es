---
title: "TransactionFlowBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## Sintaxis  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## Métodos  
 La clase TransactionFlowBindingElement no define ningún método.  
  
## Propiedades  
 La clase TransactionFlowBindingElement tiene las propiedades siguientes:  
  
### IssuedTokens  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica el requisito para un encabezado de token de seguridad emitido \(IssuedTokens de WS\-Trust\).  
  
### TransactionProtocol  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El protocolo de transacciones utilizado por el servicio para fluir las transacciones.  
  
### Transacciones  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si se admite la transacción entrante.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>