---
title: "Recuperar informaci&#243;n de instalaci&#243;n de un dominio de aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "AppDomainSetup (objeto)"
  - "dominios de la aplicación, recuperar información de instalación"
  - "recuperar información de instalación"
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Recuperar informaci&#243;n de instalaci&#243;n de un dominio de aplicaci&#243;n
Todas las instancias de un dominio de aplicación están formadas por propiedades y por información de <xref:System.AppDomainSetup>.  La información de instalación se puede recuperar de un dominio de aplicación mediante la clase <xref:System.AppDomain?displayProperty=fullName>.  Esta clase proporciona varios miembros que recuperan la información de configuración de un dominio de aplicación.  
  
 También se puede consultar el objeto **AppDomainSetup** del dominio de aplicación para obtener la información de instalación que se paso al dominio cuando se creó.  
  
 En el ejemplo siguiente se crea un nuevo dominio de aplicación y, a continuación, se imprimen varios valores de miembros en la consola.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 En el siguiente ejemplo se establece, y después se recupera, información de instalación de un dominio de aplicación.  Tenga en cuenta que `AppDomain.SetupInformation.ApplicationBase` obtiene la información de configuración.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## Vea también  
 [Hosting Overview](http://msdn.microsoft.com/es-es/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)