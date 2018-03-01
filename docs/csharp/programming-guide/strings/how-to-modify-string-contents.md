---
title: "Cómo: Modificar el contenido de cadenas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>Cómo: Modificar el contenido de cadenas (Guía de programación de C#)
Como las cadenas son *immutables*, no es posible (sin usar código no seguro) modificar el valor de un objeto de cadena después de que se haya creado. En cambio, existen muchas maneras de modificar el valor de una cadena y almacenar el resultado en un nuevo objeto de cadena. La clase <xref:System.String?displayProperty=nameWithType> proporciona métodos que funcionan en una cadena de entrada y devuelven un nuevo objeto de cadena. En muchos casos, puede asignar el nuevo objeto a la variable que contenía la cadena original. La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> proporciona métodos adicionales que funcionan de una manera similar. La clase <xref:System.Text.StringBuilder?displayProperty=nameWithType> proporciona un búfer de caracteres que puede modificar "en contexto". Puede llamar al método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> para crear un nuevo objeto de cadena que contiene el contenido actual del búfer.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de reemplazar o quitar subcadenas en una cadena especificada.  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Para tener acceso a los caracteres individuales en una cadena mediante la notación de matriz, puede usar el objeto <xref:System.Text.StringBuilder>, que sobrecarga el operador `[]` para proporcionar acceso a su búfer de caracteres interno. También puede convertir la cadena en una matriz de caracteres mediante el método <xref:System.String.ToCharArray%2A>. En el ejemplo siguiente se usa `ToCharArray` para crear la matriz. Algunos elementos de esta matriz se modifican después. Un constructor de cadena que toma una matriz de caracteres como un parámetro de entrada se llama después para crear una nueva cadena.  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se proporciona para esas situaciones poco habituales en las que puede que quiera modificar una cadena en contexto mediante código no seguro de una manera similar a matrices de caracteres de estilo C. El ejemplo muestra cómo tener acceso a los caracteres individuales "en contexto" con la palabra clave fixed. También muestra un posible efecto secundario de operaciones no seguras en cadenas que se obtienen de la manera en que el compilador de C# almacena cadenas (internos) internamente. En general, no debe usar esta técnica a no ser que sea absolutamente necesario.  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)
