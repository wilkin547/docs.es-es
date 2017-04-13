---
title: "Analizar otras cadenas en .NET Framework | Microsoft Docs"
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
  - "Tipo de datos char, analizar cadenas"
  - "enumeraciones [.NET Framework], cadenas de análisis"
  - "tipos base, analizar cadenas"
  - "analizar cadenas, otras cadenas"
  - "tipo de datos booleano, analizar cadenas"
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Analizar otras cadenas en .NET Framework
Además de cadenas numéricas y <xref:System.DateTime> se pueden analizar cadenas que representan los tipos <xref:System.Char>, <xref:System.Boolean> y <xref:System.Enum> en tipos de datos.  
  
## Char  
 El método de análisis estático asociado al tipo de datos **Char** resulta útil para convertir una cadena de un único carácter en su valor Unicode.  En el ejemplo de código siguiente se analiza una cadena en un carácter Unicode.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## Boolean  
 El tipo de datos **Boolean** tiene un método **Parse** que se puede utilizar para convertir la cadena que representa un valor Boolean en un tipo **Boolean** propiamente dicho.  En este método no hay distinción entre mayúsculas y minúsculas y se puede analizar correctamente una cadena que contenga "True" o "False." El método **Parse** asociado al tipo de datos **Boolean** también puede analizar cadenas que tienen espacios en blanco alrededor.  Si se pasa cualquier otra cadena, se produce una <xref:System.FormatException>.  
  
 En el ejemplo de código siguiente se utiliza el método **Parse** para convertir una cadena en un valor Boolean.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## Enumeración  
 Se puede usar el método estático **Parse** para inicializar un tipo de enumeración en el valor de una cadena.  Este método acepta el tipo de enumeración que se está analizando, la cadena que se va a analizar y un marcador Boolean opcional que indica si hay distinción entre mayúsculas y minúsculas.  La cadena que se va a analizar puede contener varios valores separados por comas, que pueden ir precedidos o seguidos por uno o varios espacios vacíos \(también denominados espacios en blanco\).  Cuando la cadena contiene varios valores, el valor del objeto devuelto es el valor de todos los valores especificados combinados con una operación OR bit a bit.  
  
 En el ejemplo siguiente se utiliza el método **Parse** para convertir una representación de cadena en un valor de enumeración.  A partir de la cadena se inicializa la enumeración <xref:System.DayOfWeek> en **Thursday**.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## Vea también  
 [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)   
 [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md)   
 [Conversión de tipos en .NET Framework](../../../docs/standard/base-types/type-conversion.md)