---
title: 'Palabra clave private: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: a13e9ef18b0f6452c3ff1497dc97110bc21c433d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715197"
---
# <a name="private-c-reference"></a>private (Referencia de C#)

La palabra clave `private` es un modificador de acceso de miembro.

> Esta página trata sobre el modificador de acceso `private`. La palabra clave `private` también forma parte del modificador de acceso [`private protected`](./private-protected.md).

El acceso privado es el nivel de acceso menos permisivo. Los miembros privados solo son accesibles dentro del cuerpo de la clase o el struct en el que se declaran, como en este ejemplo:

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

Los tipos anidados en el mismo cuerpo también pueden tener acceso a los miembros privados.

Hacer referencia a un miembro privado fuera de la clase o el struct en el que se declara es un error en tiempo de compilación.

Para obtener una comparación de `private` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md) y [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="example"></a>Ejemplo

En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`. Como miembros privados, solo pueden tener acceso a ellos los métodos de miembro. Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados. Se tiene acceso al miembro `name` a través de un método público, mientras que se tiene acceso al miembro `salary` a través de una propiedad pública de solo lectura. (Para obtener más información, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md)).

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a>especificación del lenguaje C#  

Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores de acceso](access-modifiers.md)
- [Niveles de accesibilidad](accessibility-levels.md)
- [Modificadores](index.md)
- [public](public.md)
- [protected](protected.md)
- [internal](internal.md)
