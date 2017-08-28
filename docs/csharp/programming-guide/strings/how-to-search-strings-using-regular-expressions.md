---
title: "Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)
La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> se puede usar para buscar cadenas. Estas búsquedas pueden tener distinta complejidad, desde ser muy sencillas hasta hacer un gran uso de expresiones regulares. A continuación se ofrecen dos ejemplos de búsqueda de cadenas usando la clase <xref:System.Text.RegularExpressions.Regex>. Para obtener más información, vea [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente es una aplicación de consola que realiza una búsqueda simple de cadenas sin distinción entre mayúsculas y minúsculas en una matriz. El método estático <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> realiza la búsqueda a partir de la cadena de búsqueda y de una cadena que contiene el modelo de búsqueda. En este caso, se usa un tercer argumento para indicar que no se debe distinguir entre mayúsculas y minúsculas. Para obtener más información, consulta <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente es una aplicación de consola que usa expresiones regulares para validar el formato de cada cadena de una matriz. La validación requiere que cada cadena tenga la forma de un número de teléfono en el que tres grupos de dígitos se separan por guiones. Los dos primeros grupos contienen tres dígitos, y el tercero, cuatro. Para ello, se usa la expresión regular `^\\d{3}-\\d{3}-\\d{4}$`. Para obtener más información, consulte [Lenguaje de expresiones regulares: Referencia rápida](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312)   
 [Lenguaje de expresiones regulares: referencia rápida](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

