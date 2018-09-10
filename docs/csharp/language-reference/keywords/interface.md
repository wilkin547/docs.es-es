---
title: interface (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 4adc7ba106e0044ba6aff94ea3180d9c8e3ded7b
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266844"
---
# <a name="interface-c-reference"></a>interface (Referencia de C#)

Una interfaz contiene solo las firmas de [métodos](../../programming-guide/classes-and-structs/methods.md), [propiedades](../../programming-guide/classes-and-structs/properties.md), [eventos](../../programming-guide/events/index.md) o [indizadores](../../programming-guide/indexers/index.md). Una clase o struct que implemente la interfaz debe implementar los miembros de la interfaz que se especifican en la definición de interfaz. En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.

Para obtener más información y ejemplos, vea [Interfaces](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Una interfaz puede ser miembro de un espacio de nombres o de una clase, y puede contener signaturas de los siguientes miembros:

- [Métodos](../../programming-guide/classes-and-structs/methods.md)

- [Propiedades](../../programming-guide/classes-and-structs/using-properties.md)

- [Indizadores](../../programming-guide/indexers/using-indexers.md)

- [Eventos](event.md)

Una interfaz puede heredar de una o varias interfaces base.

Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.

Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz. A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.

Para obtener más información detallada y ejemplos de código de la implementación de interfaces explícita, vea [Implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra la implementación de una interfaz. En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación. Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../programming-guide/index.md)  
- [Palabras clave de C#](index.md)  
- [Tipos de referencia](reference-types.md)  
- [Interfaces](../../programming-guide/interfaces/index.md)  
- [Utilizar propiedades](../../programming-guide/classes-and-structs/using-properties.md)  
- [Utilizar indizadores](../../programming-guide/indexers/using-indexers.md)  
- [class](class.md)  
- [struct](struct.md)  
- [Interfaces](../../programming-guide/interfaces/index.md)
