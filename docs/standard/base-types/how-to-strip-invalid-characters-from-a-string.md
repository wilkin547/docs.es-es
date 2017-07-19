---
title: "C&#243;mo: Quitar caracteres no v&#225;lidos de una cadena | Microsoft Docs"
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
  - "expresiones regulares, ejemplos"
  - "limpiar entrada"
  - "entrada de usuario, ejemplos"
  - "expresiones regulares de .NET Framework, ejemplos"
  - "expresiones regulares [.NET Framework], ejemplos"
  - "Regex.Replace (método)"
  - "quitar caracteres no válidos"
  - "Replace (método)"
  - "validar los datos proporcionados por el usuario"
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Quitar caracteres no v&#225;lidos de una cadena
En el ejemplo de código siguiente se usa el método estático <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> para quitar caracteres no válidos de una cadena.  
  
## Ejemplo  
 Puede utilizar el método `CleanInput` definido en este ejemplo para quitar caracteres potencialmente dañinos especificados en un campo de texto que acepta datos proporcionados por el usuario.  En este caso, `CleanInput` quita todos los caracteres no alfanuméricos excepto los puntos \(.\), los símbolos de arroba \(@\) y los guiones \(\-\), y devuelve la cadena restante.  Sin embargo, puede modificar el patrón de expresión regular para que quite cualquier carácter que no deba incluirse en una cadena de entrada.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 El modelo de expresión regular `[^\w\.@-]` coincide con cualquier carácter que no sea un carácter alfabético, un punto, un símbolo @ o un guión.  Un carácter alfabético es cualquier letra, dígito decimal o conector de puntuación como un subrayado.  Cualquier carácter que coincida con este modelo es reemplazado por <xref:System.String.Empty?displayProperty=fullName>, que es la cadena definida por el modelo de reemplazo.  Para permitir caracteres adicionales en los datos proporcionados por el usuario, agregue esos caracteres a la clase de caracteres en el patrón de expresión regular.  Por ejemplo, el patrón de expresión regular `[^\w\.@-\\%]` también permite un símbolo de porcentaje y una barra diagonal inversa en una cadena de entrada.  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)