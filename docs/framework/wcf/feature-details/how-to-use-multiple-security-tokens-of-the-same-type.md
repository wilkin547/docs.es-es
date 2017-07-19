---
title: "C&#243;mo: Utilizar m&#250;ltiples tokens de seguridad del mismo tipo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar m&#250;ltiples tokens de seguridad del mismo tipo
-   En [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, un mensaje de cliente solo contenía un token de un tipo dado.  Ahora, los mensajes de cliente pueden contener múltiples tokens de un tipo.  En este tema se muestra cómo incluir múltiples tokens del mismo tipo en un mensaje de cliente.  
  
-   Tenga en cuenta que no se puede configurar un servicio de esta manera: un servicio puede contener sólo un token auxiliar.  
  
### Utilizar múltiples tokens de seguridad del mismo tipo  
  
1.  Cree una colección vacía de elementos de enlace para rellenarla.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> llamando a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  Cree una colección <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  Agregue tokens SAML a la colección.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  Agregue la colección a <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  Agregue elementos de enlace a la colección de elementos de enlace.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  Devuelva un nuevo enlace personalizado creado a partir de la colección de elementos de enlace.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## Ejemplo  
 Lo siguiente es el método completo descrito por el procedimiento anterior.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## Vea también  
 [Security Architecture](http://msdn.microsoft.com/es-es/16593476-d36a-408d-808c-ae6fd483e28f)