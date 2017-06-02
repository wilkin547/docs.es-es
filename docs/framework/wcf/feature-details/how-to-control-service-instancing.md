---
title: "C&#243;mo controlar la creaci&#243;n de instancias de servicio | Microsoft Docs"
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
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# C&#243;mo controlar la creaci&#243;n de instancias de servicio
Establecer el modo de instancia de un servicio le permite especificar cuándo se crea \(y su objeto de servicio  asociado definido por el usuario\) <xref:System.ServiceModel.InstanceContext?displayProperty=fullName>.  Vea la enumeración de <xref:System.ServiceModel.InstanceContextMode> para los posibles modos.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los comportamientos, vea [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  Para obtener ejemplos, consulte [Comportamientos](../../../../docs/framework/wcf/samples/behaviors.md).  
  
### Para controlar la duración de instancia de servicio mediante el código  
  
1.  Aplique <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase de servicio.  
  
2.  Establezca la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> a uno de los siguientes valores: <xref:System.ServiceModel.InstanceContextMode>, <xref:System.ServiceModel.InstanceContextMode>, o <xref:System.ServiceModel.InstanceContextMode>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## Ejemplo  
 El siguiente ejemplo de código establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> del atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> en <xref:System.ServiceModel.InstanceContextMode>.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## Vea también  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>   
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>   
 <xref:System.ServiceModel.InstanceContextMode>   
 [Service: Behaviors Samples](http://msdn.microsoft.com/es-es/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)