---
title: using static (Directiva, Referencia de C#) | Microsoft Docs
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c072d365b4ecffb524b57c2328217da05a8af3ed
ms.lasthandoff: 03/13/2017

---
# <a name="using-static-directive-c-reference"></a>using static (Directiva, Referencia de C#)

La directiva `using static` designa un tipo a cuyos miembros estáticos se puede acceder sin especificar un nombre de tipo. Su sintaxis es:

```csharp
using static <fully-qualified-type-name>
```

donde *fully-qualified-type-name* es el nombre del tipo a cuyos miembros estáticos se puede hacer referencia sin especificar un nombre de tipo. Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador CS0246: "The type or namespace name '<type-name>' could not be found" (No se pudo encontrar el nombre de tipo o de espacio de nombres "<type-name>").

La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos, aunque también tenga miembros de instancia. Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.

La directiva `using static` se ha agregado en C# 6.

## <a name="reamrks"></a>Comentarios
 
Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro. Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro. Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase @System.Math.
  
[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Al eliminar la necesidad de hacer referencia explícitamente a la clase @System.Math cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:

[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.  Los miembros heredados no se importan.  Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.  Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.  
  
 `using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.  Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.  
  
 Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.  La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.  
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases @System.Console, @System.Math y @System.String estén disponibles sin tener que especificar su nombre de tipo.

[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo @System.Double. Esto habría permitido llamar al método @System.Double.TryParse(System.String,System.Double@) sin especificar un nombre de tipo. Pero esto crea un código menos legible, ya que es necesario comprobar las instrucciones `using static` para determinar el método `TryParse` de tipo numérico al que se llama.

## <a name="see-also"></a>Vea también

[using Directive](using-directive.md)  (using [Directiva, Referencia de C#])  
[Referencia de C#](../../../csharp/language-reference/index.md)   
[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  (Usar espacios de nombres)  
[Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
[Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)   

