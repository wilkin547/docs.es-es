---
title: Propiedades (F#)
description: 'Obtenga información sobre F # propiedades, que son miembros que representan valores asociados a un objeto.'
ms.date: 05/16/2016
ms.openlocfilehash: 7aa71b1801b44fedcb420b824078004c6c240dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="properties"></a>Propiedades

*Propiedades* son miembros que representan valores asociados a un objeto.


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
Las propiedades representan el "tiene un" relación en la programación orientada a objetos, que representa los datos que están asociados con instancias de objeto o, para las propiedades estáticas, con el tipo.

Puede declarar propiedades de dos maneras, dependiendo de si desea especificar explícitamente el valor subyacente (conocida también como el almacén de copias de seguridad de) para la propiedad, o si desea permitir que el compilador genere automáticamente el almacén de copia de seguridad. Por lo general, debe usar la forma más explícita si la propiedad tiene una implementación no trivial y la forma automática cuando la propiedad es simplemente un contenedor simple para un valor o una variable. Para declarar una propiedad de forma explícita, use la `member` palabra clave. Esta sintaxis declarativa va seguida de la sintaxis que especifica la `get` y `set` métodos, también denominadas *descriptores de acceso*. Las distintas formas de sintaxis explícita que se muestra en la sección de sintaxis se usan para las propiedades de lectura/escritura, de solo lectura y de solo escritura. Para las propiedades de solo lectura, definir solo un `get` método; para las propiedades de solo escritura, definir solo un `set` método. Tenga en cuenta que, cuando una propiedad tiene `get` y `set` descriptores de acceso, la sintaxis alternativa le permite especificar los atributos y modificadores de accesibilidad que son diferentes para cada descriptor de acceso, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Para propiedades de lectura/escritura, que tienen tanto un `get` y `set` /método siguiente, el orden de `get` y `set` se puede invertir. Como alternativa, puede proporcionar la sintaxis mostrada para `get` solo y la sintaxis mostrada para `set` solo en lugar de usar la sintaxis combinada. Esto resulta más fácil para comentar el individuo `get` o `set` método, si es algo que deba realizar. Esta alternativa al uso de la sintaxis combinada se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Privada valores que espera los datos para las propiedades se denominan *memorias auxiliares*. Para hacer que el compilador crea automáticamente el almacén de copia de seguridad, utilice las palabras clave `member val`, omitir el identificador automática, a continuación, proporcione una expresión para inicializar la propiedad. Si la propiedad es mutable, incluir `with get, set`. Por ejemplo, el siguiente tipo de clase incluye dos propiedades implementadas automáticamente. `Property1` es de solo lectura y se inicializa en el argumento proporcionado al constructor primario, y `Property2` es una propiedad configurable que se inicializa en una cadena vacía:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Propiedades implementadas automáticamente son parte de la inicialización de un tipo, por lo que deben incluirse antes de las definiciones de miembros, igual que `let` enlaces y `do` enlaces en una definición de tipo. Tenga en cuenta que solo se evalúa la expresión que inicialice una propiedad implementada automáticamente en la inicialización y no cada vez que se tiene acceso a la propiedad. Este comportamiento difiere del comportamiento de una propiedad implementada explícitamente. Lo que esto significa que es el código para inicializar estas propiedades se agrega al constructor de una clase. Considere el siguiente código que muestra esta diferencia:

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

**Salida**

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

El resultado del código anterior muestra que el valor de AutoProperty no cambia cuando se llama varias veces, mientras que el ExplicitProperty cambia cada vez que se llama. Esto demuestra que la expresión de una propiedad implementada automáticamente no se evalúa cada vez, como es el método de captador de propiedad explícitos.


>[!WARNING]
Hay algunas bibliotecas, por ejemplo, Entity Framework (`System.Data.Entity`) que realizan operaciones personalizadas en los constructores de clase base que no funcionan bien con la inicialización de propiedades implementadas automáticamente. En esos casos, pruebe a usar propiedades explícitas.

Propiedades pueden ser miembros de clases, estructuras, uniones discriminadas, registros, interfaces y extensiones de tipo y también se pueden definir en expresiones de objeto.

Atributos se pueden aplicar a propiedades. Para aplicar un atributo a una propiedad, escribir el atributo en una línea independiente antes de la propiedad. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

De forma predeterminada, las propiedades son públicas. Modificadores de accesibilidad también puede aplicarse a las propiedades. Para aplicar un modificador de accesibilidad, agregará inmediatamente antes del nombre de la propiedad si está diseñado para que se aplican a ambos el `get` y `set` métodos; agregarlo antes de la `get` y `set` palabras clave si es de distintos tipos de accesibilidad se requiere para cada descriptor de acceso. El *modificador de accesibilidad* puede ser uno de los siguientes: `public`, `private`, `internal`. Para más información, vea [Access Control](../access-control.md) (Control de acceso).

Las implementaciones de propiedad se ejecutan cada vez que se tiene acceso a una propiedad.


## <a name="static-and-instance-properties"></a>Estáticos y propiedades de la instancia
Propiedades pueden ser estáticos o propiedades de la instancia. Propiedades estáticas se pueden invocar sin una instancia y se usan para los valores asociados con el tipo, no a los objetos individuales. Para las propiedades estáticas, omitir el identificador automática. Self-identifier es necesario para las propiedades de instancia.

La siguiente definición de propiedad estática se basa en un escenario en el que tiene un campo estático `myStaticValue` que es el almacén de respaldo para la propiedad.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Las propiedades también pueden ser como una matriz, en cuyo caso se les llama *propiedades indizadas*. Para obtener más información, consulte [propiedades indizadas](indexed-properties.md).


## <a name="type-annotation-for-properties"></a>Anotación de tipo para las propiedades
En muchos casos, el compilador tiene información suficiente para inferir el tipo de una propiedad del tipo de la memoria auxiliar, pero puede establecer explícitamente el tipo mediante la adición de una anotación de tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Usar propiedad conjunto de descriptores de acceso
Puede establecer las propiedades que proporcionan `set` descriptores de acceso mediante el uso de la `<-` operador.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

El resultado es **20**.


## <a name="abstract-properties"></a>Propiedades abstractas
Propiedades pueden ser abstractas. Al igual que con los métodos, `abstract` simplemente significa que hay una distribución virtual asociada a la propiedad. Propiedades abstractas pueden ser verdaderamente abstractas, es decir, sin una definición de la misma clase. Por lo tanto, la clase que contiene este tipo de propiedad es una clase abstracta. Como alternativa, abstracta puede significar que una propiedad es virtual, y en ese caso, una definición debe estar presente en la misma clase. Tenga en cuenta que las propiedades abstractas no deben ser privadas, y si un descriptor de acceso es abstracto, el otro debe también ser abstracto. Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Vea también
[Miembros](index.md)

[Métodos](methods.md)
