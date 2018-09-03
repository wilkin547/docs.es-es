---
title: using static (Directiva, Referencia de C#)
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04e7368a6b6a4453f2dd07c7afdc0bffa7473ed1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43422684"
---
# <a name="using-static-directive-c-reference"></a>using static (Directiva, Referencia de C#)

La directiva `using static` designa un tipo a cuyos miembros estáticos y tipos anidados se puede acceder sin especificar un nombre de tipo. Su sintaxis es:

```csharp
using static <fully-qualified-type-name>;
```

donde *nombre-completo-del-tipo* es el nombre del tipo a cuyos miembros estáticos y tipos anidados se puede hacer referencia sin especificar un nombre de tipo. Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador [CS0246](../compiler-messages/cs0246.md): "El nombre del tipo o del espacio de nombres "tipo/espacio de nombres" no se encontró (¿falta una directiva using o una referencia de ensamblado?)".

La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos (o tipos anidados), aunque también tenga miembros de instancia. Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.

La directiva `using static` se ha agregado en C# 6.

## <a name="remarks"></a>Comentarios
 
Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro. Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro. Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase <xref:System.Math>.
  
[!code-csharp[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Al eliminar la necesidad de hacer referencia explícitamente a la clase <xref:System.Math> cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:

[!code-csharp[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.  Los miembros heredados no se importan.  Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.  Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.  
  
 `using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.  Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.  
  
 Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.  La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.  
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases <xref:System.Console>, <xref:System.Math> y <xref:System.String> estén disponibles sin tener que especificar su nombre de tipo.

[!code-csharp[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo <xref:System.Double>. Esto habría permitido llamar al método <xref:System.Double.TryParse(System.String,System.Double@)> sin especificar un nombre de tipo. Pero esto crea un código menos legible, ya que es necesario comprobar las instrucciones `using static` para determinar el método `TryParse` de tipo numérico al que se llama.

## <a name="see-also"></a>Vea también

- [using (directiva)](using-directive.md)
- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
- [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)
- [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)
- [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)
