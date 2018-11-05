---
title: Restricciones (F#)
description: Obtenga información sobre restricciones de F# que se aplican a los parámetros de tipo genérico para especificar los requisitos para un argumento de tipo en una función o tipo genérico.
ms.date: 05/16/2016
ms.openlocfilehash: 9534db4ffd195022366af8c993658bd94f375f53
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "48837378"
---
# <a name="constraints"></a>Restricciones

En este tema se describe las restricciones que se pueden aplicar a genérica parámetros para especificar los requisitos para un argumento de tipo en una función o tipo genérico de tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Comentarios

Hay varias restricciones diferentes que puede aplicar para limitar los tipos que se pueden usar en un tipo genérico. En la tabla siguiente se enumera y describe estas restricciones.

|Restricción|Sintaxis|Descripción|
|----------|------|-----------|
|Restricción de tipo|*parámetro de tipo* :&gt; *tipo*|El tipo proporcionado debe ser igual o derivado del tipo especificado, o bien, si el tipo es una interfaz, el tipo proporcionado debe implementar la interfaz.|
|Restricción null|*parámetro de tipo* : null|El tipo proporcionado debe admitir el literal null. Esto incluye todos los tipos de objetos. NET, pero no F# lista, tupla, función, clase, registro o tipos de unión.|
|Restricción de miembro explícito|[(]*parámetro de tipo* [o … o *parámetro de tipo*)]: (*firma del miembro*)|Al menos uno de los argumentos de tipo proporcionados debe tener un miembro que tiene la firma especificada; no se ha diseñado para su uso común. Los miembros deben ser explícitamente definidos en el tipo o parte de una extensión de tipo implícito sea destinos válidos para una restricción explícita del miembro.|
|Restricción de constructor|*parámetro de tipo* : (nuevo: unidad -&gt; ' un)|El tipo proporcionado debe tener un constructor predeterminado.|
|Restricción de tipo de valor|: struct|El tipo proporcionado debe ser un tipo de valor. NET.|
|Restricción de tipo de referencia|: no struct|El tipo proporcionado debe ser un tipo de referencia. NET.|
|Restricción de tipo de enumeración|: enumeración&lt;*tipo subyacente*&gt;|El tipo proporcionado debe ser un tipo enumerado que tiene el tipo subyacente especificado; no se ha diseñado para su uso común.|
|Restricción de delegado|: delegar&lt;*tupla de tipo de parámetro*, *tipo de valor devuelto*&gt;|El tipo proporcionado debe ser un tipo de delegado que tiene los argumentos especificados y devuelve el valor; no se ha diseñado para su uso común.|
|Restricción de comparación|: comparación|El tipo proporcionado debe admitir la comparación.|
|Restricción de igualdad|: igualdad|El tipo proporcionado debe admitir la igualdad.|
|Restricción no administrada|: no administrado|El tipo proporcionado debe ser un tipo no administrado. Los tipos no administrados son cualquier ciertos tipos primitivos (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), tipos de enumeración, `nativeptr<_>`, o una estructura no genérica cuyos campos son todos los tipos no administrados.|
Tendrá que agregar una restricción cuando el código tiene que usar una característica que está disponible en el tipo de restricción, pero no en los tipos en general. Por ejemplo, si utiliza la restricción de tipo para especificar un tipo de clase, puede usar cualquiera de los métodos de esa clase en la función o tipo genérico.

Especificar restricciones a veces es necesario al escribir los parámetros de tipo explícitamente, porque sin una restricción, el compilador no tiene ninguna manera de comprobar que las características que está usando estará disponibles en cualquier tipo que se puede proporcionar en tiempo de ejecución para el tipo parámetro.

Las restricciones más comunes que se usa en el código de F# son las restricciones de tipo que especifican las interfaces o clases base. Las demás restricciones se utilizan por la biblioteca de F# para implementar cierta funcionalidad, como la restricción de miembro explícito, que se utiliza para implementar la sobrecarga de operadores para los operadores aritméticos, o se proporciona principalmente porque F# admite completo conjunto de restricciones que sea compatible con common language runtime.

Durante el proceso de inferencia de tipo, existen algunas restricciones se deducen automáticamente por el compilador. Por ejemplo, si usa el `+` operador en una función, el compilador deduce una restricción de miembro explícito en tipos de variables que se usan en la expresión.

El código siguiente muestra algunas declaraciones de restricción.

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

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
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
