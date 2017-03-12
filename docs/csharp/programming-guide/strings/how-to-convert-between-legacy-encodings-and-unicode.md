---
title: "C&#243;mo: Convertir entre codificaciones heredadas y Unicode (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversiones [C#], de codificaciones heredadas a Unicode"
  - "cadenas [C#], convertir codificaciones"
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# C&#243;mo: Convertir entre codificaciones heredadas y Unicode (Gu&#237;a de programaci&#243;n de C#)
En C\#, todas las cadenas en memoria se codifican como Unicode \(UTF\-16\).  Al llevar datos desde el lugar de almacenamiento a un objeto `string`, los datos se convierten automáticamente en UTF\-16.  Si los datos solo contienen valores ASCII de 0 a 127, la conversión no requiere ningún esfuerzo adicional por su parte.  Sin embargo, si el texto de origen contiene valores de byte ASCII extendidos \(de 128 a 255\), los caracteres extendidos se interpretarán de forma predeterminada de acuerdo con la página de códigos actual.  Para especificar que el texto de origen debe interpretarse de acuerdo con una página de códigos distinta, utilice la clase <xref:System.Text.Encoding?displayProperty=fullName> como se muestra en el ejemplo siguiente.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo convertir un archivo de texto codificado en ASCII de 8 bits, interpretando el texto de origen de acuerdo con la página de códigos 737 de Windows.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#34)]  
  
## Vea también  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)