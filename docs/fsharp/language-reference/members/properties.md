---
title: Propiedades
description: 'Obtenga información sobre las propiedades de F #, que son miembros que representan valores asociados a un objeto.'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740203"
---
# <a name="properties"></a>Propiedades

*Las propiedades* son miembros que representan valores asociados a un objeto.

## <a name="syntax"></a>Sintaxis

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a>Comentarios

Las propiedades representan la relación "tiene una" en la programación orientada a objetos, que representa los datos que están asociados a instancias de objeto o, para las propiedades estáticas, con el tipo.

Puede declarar propiedades de dos maneras, en función de si desea especificar explícitamente el valor subyacente (también denominado memoria auxiliar) para la propiedad, o si desea permitir que el compilador genere automáticamente la memoria auxiliar. Por lo general, debe usar la manera más explícita si la propiedad tiene una implementación no trivial y la manera automática cuando la propiedad es simplemente un contenedor simple para un valor o una variable. Para declarar una propiedad explícitamente, use la `member` palabra clave. Esta sintaxis declarativa va seguida de la sintaxis que especifica los `get` `set` métodos y, también denominados *descriptores de acceso*. Las distintas formas de sintaxis explícita que se muestran en la sección sintaxis se utilizan para las propiedades de lectura/escritura, de solo lectura y de solo escritura. En el caso de las propiedades de solo lectura, solo se define un `get` método; en el caso de las propiedades de solo escritura, solo se define un `set` método. Tenga en cuenta que cuando una propiedad tiene los descriptores de `get` `set` acceso y, la sintaxis alternativa le permite especificar los atributos y modificadores de accesibilidad que son diferentes para cada descriptor de acceso, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

En el caso de las propiedades de lectura y escritura, que tienen un `get` `set` método y `get` , `set` se puede invertir el orden de y. Como alternativa, puede proporcionar la sintaxis que se muestra `get` solo y la sintaxis que se muestra `set` solo en lugar de usar la sintaxis combinada. De este modo, resulta más fácil comentar el `get` método o individual `set` , en caso de que sea algo que sea necesario realizar. Esta alternativa al uso de la sintaxis combinada se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Los valores privados que contienen los datos de las propiedades se denominan *almacenes de respaldo*. Para que el compilador cree automáticamente la memoria auxiliar, use las palabras clave `member val` , omita el autoidentificador y proporcione una expresión para inicializar la propiedad. Si la propiedad va a ser mutable, incluya `with get, set` . Por ejemplo, el siguiente tipo de clase incluye dos propiedades implementadas automáticamente. `Property1` es de solo lectura y se inicializa en el argumento proporcionado al constructor principal, y `Property2` es una propiedad configurable inicializada en una cadena vacía:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Las propiedades implementadas automáticamente forman parte de la inicialización de un tipo, por lo que deben incluirse antes que cualquier otra definición de miembro, al igual que los `let` enlaces y `do` enlaces en una definición de tipo. Tenga en cuenta que la expresión que Inicializa una propiedad implementada automáticamente solo se evalúa durante la inicialización y no cada vez que se tiene acceso a la propiedad. Este comportamiento es distinto del comportamiento de una propiedad implementada explícitamente. Lo que significa de forma eficaz es que el código para inicializar estas propiedades se agrega al constructor de una clase. Considere el siguiente código que muestra esta diferencia:

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

**Salida**

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

La salida del código anterior muestra que el valor de autoproperty no cambia cuando se llama varias veces, mientras que ExplicitProperty cambia cada vez que se llama. Esto demuestra que la expresión para una propiedad implementada automáticamente no se evalúa cada vez, como es el método captador de la propiedad explícita.

>[!WARNING]
>Hay algunas bibliotecas, como la Entity Framework ( `System.Data.Entity` ) que realizan operaciones personalizadas en constructores de clase base que no funcionan bien con la inicialización de propiedades implementadas automáticamente. En esos casos, pruebe a usar propiedades explícitas.

Las propiedades pueden ser miembros de clases, estructuras, uniones discriminadas, registros, interfaces y extensiones de tipo, y también pueden definirse en expresiones de objeto.

Los atributos se pueden aplicar a las propiedades. Para aplicar un atributo a una propiedad, escriba el atributo en una línea independiente antes de la propiedad. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

De forma predeterminada, las propiedades son públicas. Los modificadores de accesibilidad también se pueden aplicar a las propiedades. Para aplicar un modificador de accesibilidad, agréguelo inmediatamente antes del nombre de la propiedad si está pensado para aplicarse a los `get` métodos y `set` ; agréguelo antes de las `get` `set` palabras clave y si se requiere una accesibilidad diferente para cada descriptor de acceso. El *modificador Accessibility* puede ser uno de los siguientes: `public` , `private` , `internal` . Para obtener más información, consulta [Access Control](../access-control.md).

Las implementaciones de propiedad se ejecutan cada vez que se tiene acceso a una propiedad.

## <a name="static-and-instance-properties"></a>Propiedades estáticas y de instancia

Las propiedades pueden ser propiedades estáticas o de instancia. Las propiedades estáticas se pueden invocar sin una instancia de y se usan para los valores asociados al tipo, no con los objetos individuales. En el caso de las propiedades estáticas, omita el identificador automático. El autoidentificador es necesario para las propiedades de instancia.

La siguiente definición de propiedad estática se basa en un escenario en el que tiene un campo estático `myStaticValue` que es la memoria auxiliar para la propiedad.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Las propiedades también pueden ser de tipo matriz, en cuyo caso se denominan *propiedades indizadas*. Para obtener más información, vea [propiedades indizadas](indexed-properties.md).

## <a name="type-annotation-for-properties"></a>Anotación de tipo para propiedades

En muchos casos, el compilador tiene información suficiente para inferir el tipo de una propiedad a partir del tipo de la memoria auxiliar, pero puede establecer el tipo explícitamente agregando una anotación de tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Usar descriptores de acceso del conjunto de propiedades

Puede establecer propiedades que proporcionen `set` descriptores de acceso mediante el `<-` operador.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

El resultado es **20**.

## <a name="abstract-properties"></a>Propiedades abstractas

Las propiedades pueden ser abstractas. Como con los métodos, `abstract` solo significa que hay un envío virtual asociado a la propiedad. Las propiedades abstractas pueden ser realmente abstractas, es decir, sin una definición en la misma clase. Por lo tanto, la clase que contiene una propiedad de este tipo es una clase abstracta. Como alternativa, abstract solo puede significar que una propiedad es virtual y, en ese caso, una definición debe estar presente en la misma clase. Tenga en cuenta que las propiedades abstractas no deben ser privadas y, si un descriptor de acceso es abstracto, el otro también debe ser abstracto. Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Consulte también

- [Miembros](index.md)
- [Métodos](methods.md)
