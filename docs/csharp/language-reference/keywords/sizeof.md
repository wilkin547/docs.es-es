---
title: sizeof (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a>sizeof (Referencia de C#)
Se usa para obtener el tamaño en bytes de un tipo no administrado. Los tipos no administrados incluyen los tipos integrados que se muestran en la tabla que aparece a continuación, además de estos:  
  
-   Tipos de enumeración  
  
-   Tipos de puntero  
  
-   Structs definidos por el usuario que no contienen ningún campo o propiedad que sea un tipo de referencia  
  
 En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>Comentarios  
 A partir de la versión 2.0 de C#, la aplicación de `sizeof` a los tipos integrados ya no necesita el uso del modo [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 El operador `sizeof` no se puede sobrecargar. Los valores devueltos por el operador `sizeof` son del tipo `int`. En la tabla siguiente, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos integrados como operandos.  
  
|Expresión|Valor constante|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 (Unicode)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro. Aunque puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, el valor devuelto mediante este método no es siempre el mismo que el valor devuelto por `sizeof`. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> devuelve el tamaño una vez calculado el tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [enum](../../../csharp/language-reference/keywords/enum.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Estructuras](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)
