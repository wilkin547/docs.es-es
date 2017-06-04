---
title: "C&#243;mo: Obtener informaci&#243;n sobre tipos y miembros desde un ensamblado | Microsoft Docs"
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
  - "ensamblados [.NET Framework], obtener información"
  - "obtener información de ensamblados"
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Obtener informaci&#243;n sobre tipos y miembros desde un ensamblado
El espacio de nombres <xref:System.Reflection> contiene muchos métodos para obtener información de un ensamblado.  En esta sección se muestra uno de esos métodos.  Para obtener más información, vea [Información general sobre la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md).  
  
 En el ejemplo siguiente se obtiene información de tipo y de miembro de un ensamblado.  
  
## Ejemplo  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## Vea también  
 [Hosting Overview](http://msdn.microsoft.com/es-es/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)