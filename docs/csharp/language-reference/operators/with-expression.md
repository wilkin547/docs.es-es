---
title: Expresión with (referencia de C#)
description: Obtenga información sobre una expresión with que realiza la mutación no destructiva de registros de C#
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: d7d3758c8c5da7859974b5b50b63d2a5ca16b24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702230"
---
# <a name="with-expression-c-reference"></a>Expresión with (referencia de C#)

Disponible en C# 9.0 y versiones posteriores, se trata de una expresión `with` que genera una copia de su operando [record](../../whats-new/csharp-9.md#record-types) con las propiedades y los campos especificados modificados:

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

Como se muestra en el ejemplo anterior, se usa la sintaxis de [ inicializador de objeto](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) para especificar qué miembros se van a modificar y sus nuevos valores. En una expresión `with`, un operando izquierdo debe ser de un tipo de registro.

El resultado de una expresión `with` tiene el mismo tipo de entorno de ejecución que el operando de la expresión, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

En el caso de un miembro de tipo de referencia, cuando se copia un registro solo se copia la referencia a una instancia. Tanto la copia como el registro original tienen acceso a la misma instancia de tipo de referencia. En el ejemplo siguiente se muestra ese comportamiento:

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

Cualquier tipo de registro tiene el *constructor de copia*. Es un constructor con un único parámetro del tipo de registro contenedor. Copia el estado de su argumento en una nueva instancia de registro. Al evaluar una expresión `with`, se llama al constructor de copia para crear instancias de una nueva instancia de registro en función de un registro original. Después, la nueva instancia se actualiza según las modificaciones especificadas. De forma predeterminada, el constructor de copia es implícito, es decir, lo genera el compilador. Si tiene que personalizar la semántica de la copia de registros, declare explícitamente un constructor de copia con el comportamiento deseado. En el ejemplo siguiente se actualiza el anterior con un constructor de copia explícito. El nuevo comportamiento de copia consiste en copiar los elementos de lista en lugar de una referencia de lista cuando se copia un registro:

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea las secciones siguientes de la [nota de propuestas de características de registros](~/_csharplang/proposals/csharp-9.0/records.md):

- [Expresión `with`](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [Copiar y clonar miembros](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
