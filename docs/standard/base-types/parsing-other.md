---
title: Analizar otras cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
ms.openlocfilehash: 08e891501bbefcf8b32eff10dd7294af9d81adac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127573"
---
# <a name="parsing-other-strings-in-net"></a>Analizar otras cadenas en .NET
Además de cadenas numéricas y <xref:System.DateTime>, puede analizar cadenas que representan los tipos <xref:System.Char>, <xref:System.Boolean> y <xref:System.Enum> en tipos de datos.  
  
## <a name="char"></a>Char  
 El método de análisis estático asociado con el tipo de datos **Char** es útil para convertir una cadena que contiene un único carácter en su valor Unicode. En el ejemplo de código siguiente se analiza una cadena en un carácter Unicode.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Booleano  
 El tipo de datos **Boolean** contiene un método **Parse** que se puede usar para convertir una cadena que representa un valor Boolean en un tipo **Boolean** real. Este método no distingue mayúsculas de minúsculas y puede analizar correctamente una cadena que contenga "True" o "False". El método **Parse** asociado al tipo **Boolean** también puede analizar cadenas que estén rodeadas por espacios en blanco. Si se pasa otra cadena, se produce una excepción <xref:System.FormatException>.  
  
 En el ejemplo de código siguiente se usa el método **Parse** para convertir una cadena en un valor Boolean.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Enumeración  
 Puede usar el método **Parse** estático para inicializar un tipo de enumeración en el valor de una cadena. Este método acepta el tipo de enumeración que se está analizando, la cadena que se va a analizar y una marca Boolean opcional que indica si el análisis distingue mayúsculas de minúsculas. La cadena que se va a analizar puede contener varios valores separados por comas, que pueden ir precedidos o seguidos de uno o varios espacios vacíos (también denominados espacios en blanco). Cuando la cadena contiene varios valores, el valor del objeto devuelto es el valor de todos los valores especificados combinados con una operación OR bit a bit.  
  
 En el ejemplo siguiente se usa el método **Parse** para convertir una representación de cadena en un valor de enumeración. La enumeración <xref:System.DayOfWeek> se inicializa en **Thursday** desde una cadena.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)
- [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
- [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)
