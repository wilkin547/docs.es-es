---
title: "C&#243;mo: Crear un contrato de Windows Communication Foundation con una clase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# C&#243;mo: Crear un contrato de Windows Communication Foundation con una clase
La manera preferida de crear un contrato [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es utilizar una interfaz.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo definir un contrato de servicios](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).Una alternativa, descrita aquí, es crear una clase y después aplicar el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
>  `[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo.Lo mismo se aplica a `[OperationContract]` y `[OperationContractAttribute]`.En cada caso el anterior es una forma abreviada del último.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los contratos de servicio, vea [Diseño de contratos de servicios](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### Creación de un contrato de Windows Communication Foundation con una clase  
  
1.  Cree una nueva clase mediante [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C\# o cualquier otro lenguaje de Common Language Runtime.  
  
2.  Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3.  Cree los métodos en la clase.  
  
4.  Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada método que debe exponerse como parte del contrato público de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Ejemplo  
 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un modelo de mensaje solicitud\-respuesta.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] este modelo de mensajes, vea [Creación de un contrato de solicitud\-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).Puede crear y utilizar también otros modelos de mensaje estableciendo las propiedades del atributo.Para obtener más ejemplos, vea [Cómo crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Creación de un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>