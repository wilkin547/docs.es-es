---
title: 'Registros: Guía de programación de C#'
description: Obtenga información sobre los tipos de registros y cómo crearlos
ms.date: 02/26/2021
helpviewer_keywords:
- records [C#]
- C# language, records
ms.openlocfilehash: a45ed08da18e58f11793d6874d7275d9f5216be4
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260043"
---
# <a name="records-c-programming-guide"></a>Registros (Guía de programación de C#)

Un [registro](../../language-reference/builtin-types/record.md) es una [clase](../../language-reference/keywords/class.md) que proporciona sintaxis y comportamiento especiales para trabajar con modelos de datos. Para obtener más información sobre las clases, consulte [Clases (Guía de programación de C#)](classes.md).

## <a name="when-to-use-records"></a>Cuándo se usan los registros

Considere la posibilidad de usar un registro en lugar de una clase en los siguientes escenarios:

* Desea definir un tipo de referencia para el que los objetos son inmutables.
* Desea definir un modelo de datos que dependa de la [igualdad de valores](../statements-expressions-operators/equality-comparisons.md#value-equality).

### <a name="immutability"></a>Inmutabilidad

Un tipo inmutable es aquél que impide cambiar cualquier valor de propiedad o campo de un objeto una vez creada su instancia. La inmutabilidad puede ser útil cuando se necesita que un tipo sea seguro para los subprocesos o si depende de que un código hash quede igual en una tabla hash. Los registros proporcionan una sintaxis concisa para crear y trabajar con tipos inmutables.

La inmutabilidad no es adecuada para todos los escenarios de datos. Por ejemplo, [Entity Framework Core](/ef/core/) no admite la actualización con tipos de entidad inmutables.

### <a name="value-equality"></a>Igualdad de valores

En el caso de los registros, la igualdad de valores significa que dos variables de un tipo de registro son iguales si los tipos coinciden y todos los valores de propiedad y campo coinciden. Para otros tipos de referencia, como las clases, la igualdad significa [igualdad de referencias](../statements-expressions-operators/equality-comparisons.md#reference-equality). Es decir, dos variables de un tipo de clase son iguales si hacen referencia al mismo objeto. Los métodos y operadores que determinan la igualdad de dos instancias de registro usan la igualdad de valores.

No todos los modelos de datos funcionan bien con la igualdad de valores. Por ejemplo, [Entity Framework Core](/ef/core/) depende de la igualdad de referencias para garantizar que solo usa una instancia de un tipo de entidad para lo que es conceptualmente una entidad. Por esta razón, los tipos de registro no son adecuados para su uso como tipos de entidad en Entity Framework Core.

## <a name="how-records-differ-from-classes"></a>Diferencias entre los registros y las clases

La misma sintaxis que [declara](classes.md#declaring-classes) y [crea instancias](classes.md#creating-objects) de clases se puede usar con los registros. Basta con sustituir la palabra clave `record` por la palabra clave `class`. Del mismo modo, los registros admiten la misma sintaxis para expresar las relaciones de herencia. Los registros se diferencian de las clases de las siguientes maneras:

* Puede usar [parámetros posicionales](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition) para crear un tipo y sus instancias con propiedades inmutables.
* Los mismos métodos y operadores que indican la igualdad o desigualdad de la referencia en las clases (como <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> y `==`), indican la [igualdad o desigualdad de valores](../../language-reference/builtin-types/record.md#value-equality) en los registros.
* Puede usar una [expresión `with`](../../language-reference/builtin-types/record.md#nondestructive-mutation) para crear una copia de un objeto inmutable con nuevos valores en las propiedades seleccionadas.
* El método `ToString` de un registro crea una cadena con formato que muestra el nombre de tipo de un objeto y los nombres y valores de todas sus propiedades públicas.
* Un registro puede [heredar de otro registro](../../language-reference/builtin-types/record.md#inheritance). Un registro no puede heredar de una clase y una clase no puede heredar de un registro.

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se define un registro público que usa parámetros posicionales para declarar y crear instancias de un registro. A continuación, imprime el nombre de tipo y los valores de propiedad:

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="InstantiatePositional":::

En el ejemplo siguiente se muestra la igualdad de valores en los registros:

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="Equality":::

En el ejemplo siguiente se muestra el uso de una expresión `with` para copiar un objeto inmutable y cambiar una de las propiedades:

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="WithExpressions":::

Para obtener más información, consulte [Registros (Referencia de C#)](../../language-reference/builtin-types/record.md).
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Clases (Guía de programación de C#)](classes.md)
- [Registros (Referencia de C#)](../../language-reference/builtin-types/record.md)
- [Guía de programación de C#](../index.md)
- [Programación orientada a objetos](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [Polimorfismo](polymorphism.md)
- [Nombres de identificador](../inside-a-program/identifier-names.md)
- [Miembros](members.md)
- [Métodos](methods.md)
- [Constructores](constructors.md)
- [Finalizadores](destructors.md)
- [Objects](objects.md)
