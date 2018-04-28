---
title: Propiedades indizadas (F#)
description: 'Obtenga información acerca de las propiedades indizadas de F #, que son propiedades que proporcionan acceso de matriz a los datos ordenados.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a>Propiedades indizadas

*Propiedades indizadas* propiedades que proporcionan acceso de la matriz a se ordenan los datos.


## <a name="syntax"></a>Sintaxis

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Comentarios
Las tres formas de la sintaxis anterior muestran cómo definir propiedades indizadas que tienen tanto una `get` y un `set` método, tienen un `get` método únicamente, o tiene un `set` método solo. También puede combinar ambos la sintaxis mostrada para get únicamente y la sintaxis mostrada para set únicamente y generar una propiedad que tenga get y set. Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer métodos.

Cuando el *PropertyName* es `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada. A *propiedad indizada predeterminada* es una propiedad que se puede tener acceso mediante sintaxis parecida a la matriz en la instancia del objeto. Por ejemplo, si `obj` es un objeto del tipo que define esta propiedad, la sintaxis `obj.[index]` se usa para tener acceso a la propiedad.

La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis. Por ejemplo, si la propiedad es `Ordinal`, se escribe `obj.Ordinal(index)` para tener acceso a él.

Independientemente de qué forma utilice, debe utilizar siempre el formulario currificado para el `set` método en una propiedad indizada. Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra la definición y el uso del valor predeterminado y las propiedades indizadas no predeterminadas que tienen get y set métodos.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Salida

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Propiedades indizadas con varias Variables de índice
Propiedades indizadas pueden tener más de una variable de índice. En ese caso, las variables están separadas por comas cuando se utiliza la propiedad. El método set de esta propiedad debe tener dos argumentos currificadas, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.

El código siguiente muestra el uso de una propiedad indizada con varias variables de índice.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a>Vea también
[Miembros](index.md)
