---
description: using static (Directiva, Referencia de C#)
title: using static (Directiva, Referencia de C#)
ms.date: 03/10/2017
f1_keywords:
- using-static_CSharpKeyword
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: d117d4423a2f7c782cd6365a73e6c18298d89abc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162237"
---
# <a name="using-static-directive-c-reference"></a>using static (Directiva, Referencia de C#)

La directiva `using static` designa un tipo a cuyos miembros estáticos y tipos anidados se puede acceder sin especificar un nombre de tipo. Su sintaxis es:

```csharp
using static <fully-qualified-type-name>;
```

donde *nombre-completo-del-tipo* es el nombre del tipo a cuyos miembros estáticos y tipos anidados se puede hacer referencia sin especificar un nombre de tipo. Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador [CS0246](../compiler-messages/cs0246.md): "No se pudo encontrar el tipo o el nombre del espacio de nombres 'type/namespace' (¿falta una directiva using o una referencia de ensamblado?)".

La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos (o tipos anidados), aunque también tenga miembros de instancia. Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.

La directiva `using static` se ha agregado en C# 6.

## <a name="remarks"></a>Comentarios

Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro. Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro. Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase <xref:System.Math>.

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Al eliminar la necesidad de hacer referencia explícitamente a la clase <xref:System.Math> cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.  Los miembros heredados no se importan.  Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.  Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.

 `using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.  Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.

 Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.  La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases <xref:System.Console>, <xref:System.Math> y <xref:System.String> estén disponibles sin tener que especificar su nombre de tipo.

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo <xref:System.Double>. Esto habría permitido llamar al método <xref:System.Double.TryParse(System.String,System.Double@)> sin especificar un nombre de tipo. Sin embargo, el código que se crea es menos legible, ya que es necesario comprobar las directivas `using static` para determinar el método `TryParse` del tipo numérico al que se llama.

## <a name="see-also"></a>Vea también

- [using (directiva)](using-directive.md)
- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Utilizar espacios de nombres](../../programming-guide/namespaces/using-namespaces.md)
- [Espacios de nombres](../../programming-guide/namespaces/index.md)
