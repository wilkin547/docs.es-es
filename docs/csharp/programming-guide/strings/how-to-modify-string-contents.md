---
title: "Cómo: Modificar el contenido de cadenas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>Cómo: Modificar el contenido de cadenas (Guía de programación de C#)
Como las cadenas son *immutables*, no es posible (sin usar código no seguro) modificar el valor de un objeto de cadena después de que se haya creado. En cambio, existen muchas maneras de modificar el valor de una cadena y almacenar el resultado en un nuevo objeto de cadena. La clase <xref:System.String?displayProperty=fullName> proporciona métodos que funcionan en una cadena de entrada y devuelven un nuevo objeto de cadena. En muchos casos, puede asignar el nuevo objeto a la variable que contenía la cadena original. La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> proporciona métodos adicionales que funcionan de una manera similar. La clase <xref:System.Text.StringBuilder?displayProperty=fullName> proporciona un búfer de caracteres que puede modificar "en contexto". Puede llamar al método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> para crear un nuevo objeto de cadena que contiene el contenido actual del búfer.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de reemplazar o quitar subcadenas en una cadena especificada.  
  
 [!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Para tener acceso a los caracteres individuales en una cadena mediante la notación de matriz, puede usar el objeto <xref:System.Text.StringBuilder>, que sobrecarga el operador `[]` para proporcionar acceso a su búfer de caracteres interno. También puede convertir la cadena en una matriz de caracteres mediante el método <xref:System.String.ToCharArray%2A>. En el ejemplo siguiente se usa `ToCharArray` para crear la matriz. Algunos elementos de esta matriz se modifican después. Un constructor de cadena que toma una matriz de caracteres como un parámetro de entrada se llama después para crear una nueva cadena.  
  
 [!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se proporciona para esas situaciones poco habituales en las que puede que quiera modificar una cadena en contexto mediante código no seguro de una manera similar a matrices de caracteres de estilo C. El ejemplo muestra cómo tener acceso a los caracteres individuales "en contexto" con la palabra clave fixed. También muestra un posible efecto secundario de operaciones no seguras en cadenas que se obtienen de la manera en que el compilador de C# almacena cadenas (internos) internamente. En general, no debe usar esta técnica a no ser que sea absolutamente necesario.  
  
 [!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)

