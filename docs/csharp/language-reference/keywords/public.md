---
title: Palabra clave public (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: b2e09bdb16d6128d69a3eb33cf2cffd4cba60376
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "43518191"
---
# <a name="public-c-reference"></a>public (Referencia de C#)

La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo. El acceso público es el nivel de acceso más permisivo. No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Vea [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](accessibility-levels.md) para obtener más información.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se declaran dos clases, `PointTest` y `MainClass`. Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `MainClass`.

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

Si cambia el nivel de acceso `public` a [private](private.md) o [protected](protected.md), obtendrá el siguiente mensaje de error:

'PointTest.y' no es accesible debido a su nivel de protección.

## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Palabras clave de C#](index.md)
- [Modificadores de acceso](access-modifiers.md)
- [Niveles de accesibilidad](accessibility-levels.md)
- [Modificadores](modifiers.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)