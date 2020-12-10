---
title: Tipos de valor que aceptan valores NULL
description: 'Aprenda a usar tipos de valor que aceptan valores NULL, una manera de representar tipos de valor que también pueden ser null en F #.'
ms.date: 11/19/2020
ms.openlocfilehash: e28cbfc57c5631573f46ac36462517cf011e96d2
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009643"
---
# <a name="nullable-value-types"></a>Tipos de valor que aceptan valores NULL

Un _tipo de valor que acepta valores NULL_ `Nullable<'T>` representa cualquier tipo de [struct](structures.md) que también podría ser `null` . Esto resulta útil al interactuar con bibliotecas y componentes que pueden optar por representar estos tipos de tipos, como enteros, con un `null` valor por motivos de eficiencia. El tipo subyacente que respalda esta construcción es <xref:System.Nullable%601?displayProperty=nameWithType> .

## <a name="syntax"></a>Syntax

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a>Declarar y asignar valores

Declarar un tipo de valor que acepta valores NULL es igual que declarar cualquier tipo de contenedor en F #:

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

También puede Elide el parámetro de tipo genérico y permitir que la inferencia de tipos lo resuelva:

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

Para asignar a un tipo de valor que acepta valores NULL, también debe ser explícito. No hay ninguna conversión implícita para los tipos de valor que aceptan valores NULL definidos por F #:

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a>Asignar null

No se puede asignar directamente `null` a un tipo de valor que acepta valores NULL. Use `Nullable()` en su lugar:

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

Esto se debe `Nullable<'T>` `null` a que no tiene un valor adecuado.

## <a name="pass-and-assign-to-members"></a>Pasar y asignar a miembros

Una diferencia clave entre trabajar con miembros y valores de F # es que los tipos de valor que aceptan valores NULL se pueden inferir implícitamente al trabajar con miembros. Considere el siguiente método que toma un tipo de valor que acepta valores NULL como entrada:

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

En el ejemplo anterior, puede pasar `12` al método `M` . También puede asignar `12` a la propiedad auto `NVT` . Si la entrada se puede construir como un tipo de valor que acepta valores NULL y coincide con el tipo de destino, el compilador de F # convertirá implícitamente dichas llamadas o asignaciones.

## <a name="examine-a-nullable-value-type-instance"></a>Examinar una instancia de tipo de valor que acepta valores NULL

A diferencia de [las opciones](options.md), que son una construcción generalizada para representar un valor posible, los tipos de valor que aceptan valores NULL no se usan con la coincidencia de patrones. En su lugar, debe usar una [`if`](conditional-expressions-if-then-else.md) expresión y comprobar la `HasValue` propiedad.

Para obtener el valor subyacente, utilice la `Value` propiedad después de una `HasValue` comprobación, como la siguiente:

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a>Operadores que aceptan valores NULL

Las operaciones con tipos de valor que aceptan valores NULL, como aritmética o comparación, pueden requerir el uso de [operadores que aceptan valores NULL](symbol-and-operator-reference/nullable-operators.md).

Puede convertir de un tipo de valor que acepta valores NULL a otro usando operadores de conversión del `FSharp.Linq` espacio de nombres:

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

También puede usar un operador que no acepte valores NULL adecuado para convertir a un tipo primitivo y arriesgar una excepción si no tiene ningún valor:

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

También puede usar operadores que aceptan valores NULL para la comprobación `HasValue` y `Value` :

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

La `?>` comparación comprueba si el lado izquierdo admite valores NULL y solo se realiza correctamente si tiene un valor. Es equivalente a la línea siguiente.

## <a name="see-also"></a>Consulte también

- [Estructuras](structures.md)
- [Opciones de F #](options.md)
