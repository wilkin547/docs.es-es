---
title: Restricciones
description: Obtenga información F# sobre las restricciones que se aplican a los parámetros de tipo genérico para especificar los requisitos de un argumento de tipo en una función o un tipo genérico.
ms.date: 05/16/2016
ms.openlocfilehash: 9912ba63138d893a7c616661dd2b1cbdbe51916c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736790"
---
# <a name="constraints"></a>Restricciones

En este tema se describen las restricciones que se pueden aplicar a los parámetros de tipo genérico para especificar los requisitos de un argumento de tipo en una función o un tipo genérico.

## <a name="syntax"></a>Sintaxis

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Comentarios

Hay varias restricciones diferentes que puede aplicar para limitar los tipos que se pueden usar en un tipo genérico. En la tabla siguiente se enumeran y se describen estas restricciones.

|Restricción|Sintaxis|Descripción|
|----------|------|-----------|
|Restricción de tipo|*type-parameter* : &gt; *Type*|El tipo proporcionado debe ser igual o derivarse del tipo especificado, o bien, si el tipo es una interfaz, el tipo proporcionado debe implementar la interfaz.|
|Restricción null|*type-parameter* : null|El tipo proporcionado debe admitir el literal null. Esto incluye todos los tipos de objetos de F# .net, pero no los tipos de lista, tupla, función, clase, registro o Unión.|
|Restricción de miembro explícita|[(]*parámetro de tipo* [o … o *parámetro de tipo*)]: (*firma del miembro*)|Al menos uno de los argumentos de tipo proporcionados debe tener un miembro que tenga la firma especificada; no está pensado para su uso común. Los miembros deben estar definidos explícitamente en el tipo o parte de una extensión de tipo implícita para ser destinos válidos para una restricción de miembro explícita.|
|Restricción de constructor|*type-parameter* : (New: unit-&gt; ' a)|El tipo proporcionado debe tener un constructor sin parámetros.|
|Restricción de tipo de valor|: struct|El tipo proporcionado debe ser un tipo de valor de .NET.|
|Restricción de tipo de referencia|: no struct|El tipo proporcionado debe ser un tipo de referencia de .NET.|
|Restricción de tipo de enumeración|: enum&lt;*underlying-type*&gt;|El tipo proporcionado debe ser un tipo enumerado que tenga el tipo subyacente especificado. no está pensado para su uso común.|
|Restricción de delegado|: delegate&lt;*tuple-parameter-type*, *return-type*&gt;|El tipo proporcionado debe ser un tipo de delegado que tenga los argumentos y el valor devuelto especificados. no está pensado para su uso común.|
|Restricción de comparación|: comparación|El tipo proporcionado debe admitir la comparación.|
|Restricción de igualdad|: igualdad|El tipo proporcionado debe admitir la igualdad.|
|Restricción no administrada|: no administrado|El tipo proporcionado debe ser un tipo no administrado. Los tipos no administrados son determinados tipos primitivos (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, 0, 1, 2 o 3), tipos de enumeración, 4 o un no genérico estructura cuyos campos son tipos no administrados.|

Tiene que agregar una restricción cuando el código tiene que usar una característica que está disponible en el tipo de restricción, pero no en los tipos en general. Por ejemplo, si usa la restricción de tipo para especificar un tipo de clase, puede usar cualquiera de los métodos de esa clase en la función o el tipo genérico.

A veces se requiere la especificación de restricciones cuando se escriben parámetros de tipo de forma explícita, ya que sin una restricción, el compilador no tiene ninguna manera de comprobar que las características que está usando estarán disponibles en cualquier tipo que se pueda proporcionar en tiempo de ejecución para el tipo parámetro.

Las restricciones más comunes que se usan en el F# código son restricciones de tipo que especifican clases base o interfaces. La F# biblioteca usa las demás restricciones para implementar ciertas funciones, como la restricción explícita de miembros, que se usa para implementar la sobrecarga de operadores para los operadores aritméticos, o se proporcionan principalmente porque F# admite el conjunto completo de restricciones admitidas por el Common Language Runtime.

Durante el proceso de inferencia de tipos, el compilador deduce algunas restricciones automáticamente. Por ejemplo, si usa el operador `+` en una función, el compilador deduce una restricción de miembro explícita en los tipos de variables que se usan en la expresión.

En el código siguiente se muestran algunas declaraciones de restricción:

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>Vea también

- [Genéricos](index.md)
- [Restricciones](constraints.md)
