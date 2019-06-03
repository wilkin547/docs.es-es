---
title: 'sizeof: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422400"
---
# <a name="sizeof-c-reference"></a>sizeof (Referencia de C#)

Se usa para obtener el tamaño en bytes de un tipo no administrado.

Los tipos no administrados incluyen:

- Los tipos simples se enumeran en la tabla siguiente:

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

- Tipos de enumeración.

- Tipos de puntero.

- Estructuras definidas por el usuario que no contienen los campos de instancia o las propiedades de instancia implementadas automáticamente que son tipos de referencia o tipos construidos.

En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a>Comentarios

A partir de la versión 2.0 de C#, para aplicar `sizeof` a tipos simples o de enumeración ya no se requiere que el código se compile en un contexto [unsafe](unsafe.md).

El operador `sizeof` no se puede sobrecargar. Los valores devueltos por el operador `sizeof` son del tipo `int`. En la tabla anterior, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos simples como operandos.

Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro. Aunque puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, el valor devuelto mediante este método no es siempre el mismo que el valor devuelto por `sizeof`. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> devuelve el tamaño una vez calculado el tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [enum](enum.md)
- [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md)
- [Structs](../../programming-guide/classes-and-structs/structs.md)
- [Constantes](../../programming-guide/classes-and-structs/constants.md)
