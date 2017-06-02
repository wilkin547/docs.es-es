---
title: "Cadenas de relleno en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cadenas de relleno"
  - "PadLeft (método)"
  - "PadRight (método)"
  - "cadenas [.NET Framework], relleno"
  - "espacio en blanco"
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Cadenas de relleno en .NET Framework
Utilice uno de los siguientes métodos <xref:System.String> para crear una nueva cadena formada por una cadena original que se rellena con caracteres iniciales o finales hasta alcanzar una longitud total especificada.  El carácter de relleno puede ser un espacio o un carácter especificado y, por lo tanto, la cadena parece estar alineada a la derecha o a la izquierda.  
  
|Nombre del método|Utilice|  
|-----------------------|-------------|  
|<xref:System.String.PadLeft%2A?displayProperty=fullName>|Rellena una cadena con caracteres iniciales hasta alcanzar la longitud total especificada.|  
|<xref:System.String.PadRight%2A?displayProperty=fullName>|Rellena una cadena con caracteres finales hasta alcanzar la longitud total especificada.|  
  
## PadLeft  
 El método <xref:System.String.PadLeft%2A?displayProperty=fullName> crea una nueva cadena concatenando caracteres de relleno iniciales a una cadena original hasta alcanzar una longitud total especificada.  El método <xref:System.String.PadLeft%28System.Int32%29?displayProperty=fullName> utiliza el espacio en blanco como carácter de relleno y el método <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=fullName> le permite especificar su propio carácter de relleno.  
  
 En el siguiente ejemplo de código, se utiliza el método <xref:System.String.PadLeft%2A> para crear una nueva cadena con una longitud de veinte caracteres.  En el ejemplo, se muestra "`--------Hello World!`" en la consola.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## PadRight  
 El método <xref:System.String.PadRight%2A?displayProperty=fullName> crea una nueva cadena concatenando caracteres de relleno finales a una cadena original hasta alcanzar una longitud total especificada.  El método <xref:System.String.PadRight%28System.Int32%29?displayProperty=fullName> utiliza el espacio en blanco como carácter de relleno y el método <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=fullName> le permite especificar su propio carácter de relleno.  
  
 En el siguiente ejemplo de código se utiliza el método <xref:System.String.PadRight%2A> para crear una nueva cadena con una longitud de veinte caracteres.  El ejemplo muestra "`Hello World!--------`" en la consola.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## Vea también  
 [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)