---
title: "C&#243;mo: Configurar un dominio de aplicaci&#243;n | Microsoft Docs"
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
  - "dominios de la aplicación, configurar"
  - "ApplicationBase (propiedad)"
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Configurar un dominio de aplicaci&#243;n
Se puede proporcionar a Common Language Runtime información de configuración de un nuevo dominio de aplicación mediante la clase <xref:System.AppDomainSetup>.  Al crear dominios de aplicación propios, la propiedad más importante es <xref:System.AppDomainSetup.ApplicationBase%2A>.  Las demás propiedades **AppDomainSetup** las usan principalmente los hosts de motor en tiempo de ejecución para configurar dominios de aplicación concretos.  
  
 La propiedad **ApplicationBase** define el directorio raíz de la aplicación.  Cuando el motor en tiempo de ejecución tiene que satisfacer una solicitud de tipo, busca el ensamblado que contiene el tipo en el directorio que especifica la propiedad **ApplicationBase**.  
  
> [!NOTE]
>  Un nuevo dominio de aplicación sólo hereda la propiedad **ApplicationBase** de su correspondiente creador.  
  
 En el ejemplo siguiente se crea una instancia de la clase **AppDomainSetup**, se usa esta clase para crear un nuevo dominio de aplicación, se escribe la información en la consola y, después, se descarga el dominio de aplicación.  
  
## Ejemplo  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## Vea también  
 [Hosting Overview](http://msdn.microsoft.com/es-es/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)