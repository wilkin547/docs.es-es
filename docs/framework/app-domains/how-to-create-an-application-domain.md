---
title: "C&#243;mo: Crear un dominio de aplicaci&#243;n | Microsoft Docs"
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
  - "dominios de aplicación, crear"
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un dominio de aplicaci&#243;n
Un host de Common Language Runtime crea dominios de aplicación automáticamente cuando son necesarios.  No obstante, el usuario puede crear sus propios dominios de aplicación y cargarlos en ensamblados para administrarlos de forma personalizada.  También se pueden crear dominios de aplicación desde los que se ejecuta código.  
  
 Se puede crear un nuevo dominio de aplicación con uno de los métodos sobrecargados **CreateDomain** de la clase <xref:System.AppDomain?displayProperty=fullName>.  A un dominio de aplicación se le puede dar un nombre, que se usa para hacer referencia al dominio.  
  
 En el ejemplo siguiente se crea un nuevo dominio de aplicación, se le asigna el nombre `MyDomain` y, a continuación, se imprime en la consola el nombre del dominio host y el dominio de aplicación secundario recién creado.  
  
## Ejemplo  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## Vea también  
 [Hosting Overview](http://msdn.microsoft.com/es-es/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)