---
title: Propiedades (F#)
description: 'Obtenga información sobre F # propiedades, que son miembros que representan los valores asociados a un objeto.'
ms.date: 05/16/2016
ms.openlocfilehash: 75d21415b44ccc1c26ef5f478d5f5de20c3412e8
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50043652"
---
# <a name="properties"></a><span data-ttu-id="a9309-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a9309-103">Properties</span></span>

<span data-ttu-id="a9309-104">*Propiedades* son miembros que representan los valores asociados a un objeto.</span><span class="sxs-lookup"><span data-stu-id="a9309-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9309-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9309-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="a9309-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9309-106">Remarks</span></span>

<span data-ttu-id="a9309-107">Las propiedades representan el "tiene un" relación en la programación orientada a objetos, que representa los datos asociados con instancias de objeto o, para las propiedades estáticas, con el tipo.</span><span class="sxs-lookup"><span data-stu-id="a9309-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="a9309-108">Puede declarar propiedades de dos maneras, dependiendo de si desea especificar explícitamente el valor subyacente (también denominado almacén de respaldo) para la propiedad, o si desea permitir que el compilador genere automáticamente la memoria auxiliar para usted.</span><span class="sxs-lookup"><span data-stu-id="a9309-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="a9309-109">Por lo general, debe usar la forma más explícita si la propiedad tiene una implementación no trivial y la forma automática cuando la propiedad es un simple contenedor para un valor o una variable.</span><span class="sxs-lookup"><span data-stu-id="a9309-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="a9309-110">Para declarar explícitamente una propiedad, utilice el `member` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a9309-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="a9309-111">Esta sintaxis declarativa va seguida de la sintaxis que especifica el `get` y `set` métodos, también denominados *descriptores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="a9309-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="a9309-112">Las formas de la sintaxis explícita que se muestra en la sección de sintaxis se usan para lectura/escritura, las propiedades de solo lectura y de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="a9309-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="a9309-113">Para las propiedades de solo lectura, definir únicamente un `get` método; para las propiedades de solo escritura, definir únicamente un `set` método.</span><span class="sxs-lookup"><span data-stu-id="a9309-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="a9309-114">Tenga en cuenta que cuando una propiedad tiene `get` y `set` descriptores de acceso, la sintaxis alternativa le permite especificar los atributos y modificadores de accesibilidad que son diferentes para cada descriptor de acceso, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9309-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="a9309-115">Para las propiedades de lectura/escritura, que tienen ambos un `get` y `set` método, el orden de `get` y `set` se puede invertir.</span><span class="sxs-lookup"><span data-stu-id="a9309-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="a9309-116">Como alternativa, puede proporcionar la sintaxis mostrada para `get` sólo y la sintaxis mostrada para `set` sólo en lugar de usar la sintaxis combinada.</span><span class="sxs-lookup"><span data-stu-id="a9309-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="a9309-117">Esto resulta más fácil para comentar el individuo `get` o `set` método, si eso es algo que deba hacer.</span><span class="sxs-lookup"><span data-stu-id="a9309-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="a9309-118">Esta alternativa al uso de la sintaxis combinada se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9309-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="a9309-119">Suspensión se llama a los datos para las propiedades de los valores privados *memorias*.</span><span class="sxs-lookup"><span data-stu-id="a9309-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="a9309-120">Para que el compilador cree automáticamente el almacén de respaldo, use las palabras clave `member val`, omitir el identificador automática, a continuación, escriba una expresión para inicializar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="a9309-121">Si la propiedad se va a ser mutables, incluya `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="a9309-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="a9309-122">Por ejemplo, el siguiente tipo de clase incluye dos propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a9309-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="a9309-123">`Property1` es de solo lectura y se inicializa en el argumento proporcionado al constructor principal, y `Property2` es una propiedad configurable que se inicializa en una cadena vacía:</span><span class="sxs-lookup"><span data-stu-id="a9309-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="a9309-124">Las propiedades implementadas automáticamente forman parte de la inicialización de un tipo, por lo que deben incluirse antes de las definiciones de miembros, al igual que `let` enlaces y `do` enlaces en una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="a9309-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="a9309-125">Tenga en cuenta que solo se evalúa la expresión que inicialice una propiedad implementada automáticamente en la inicialización y no cada vez que se tiene acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="a9309-126">Es este comportamiento difiere del comportamiento de una propiedad implementada explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a9309-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="a9309-127">Lo que esto significa que es el código para inicializar estas propiedades se agrega al constructor de una clase.</span><span class="sxs-lookup"><span data-stu-id="a9309-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="a9309-128">Tenga en cuenta el siguiente código que se muestra esta diferencia:</span><span class="sxs-lookup"><span data-stu-id="a9309-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="a9309-129">**Salida**</span><span class="sxs-lookup"><span data-stu-id="a9309-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="a9309-130">El resultado del código anterior muestra que el valor de AutoProperty no cambia cuando se llama varias veces, mientras que el ExplicitProperty cambia cada vez que se llama.</span><span class="sxs-lookup"><span data-stu-id="a9309-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="a9309-131">Esto demuestra que la expresión para una propiedad implementada automáticamente no se evalúa cada vez, como es el método Get para la propiedad explícita.</span><span class="sxs-lookup"><span data-stu-id="a9309-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
<span data-ttu-id="a9309-132">Hay algunas bibliotecas, como Entity Framework (`System.Data.Entity`) que realizan las operaciones personalizadas en los constructores de clase base que no funcionan bien con la inicialización de las propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a9309-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="a9309-133">En esos casos, pruebe a usar las propiedades explícitas.</span><span class="sxs-lookup"><span data-stu-id="a9309-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="a9309-134">Las propiedades pueden ser miembros de clases, estructuras, uniones discriminadas, registros, interfaces y las extensiones de tipo y también se pueden definir en expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="a9309-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="a9309-135">Atributos pueden aplicarse a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a9309-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="a9309-136">Para aplicar un atributo a una propiedad, escribir el atributo en una línea independiente antes de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="a9309-137">Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="a9309-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="a9309-138">De forma predeterminada, las propiedades son públicas.</span><span class="sxs-lookup"><span data-stu-id="a9309-138">By default, properties are public.</span></span> <span data-ttu-id="a9309-139">Modificadores de accesibilidad también se pueden aplicar a propiedades.</span><span class="sxs-lookup"><span data-stu-id="a9309-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="a9309-140">Para aplicar un modificador de accesibilidad, agréguela inmediatamente antes del nombre de la propiedad si está diseñada para que se aplican a ambos el `get` y `set` métodos; antes de agregar el `get` y `set` palabras clave si es la accesibilidad diferente se requiere para cada descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="a9309-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="a9309-141">El *modificador de accesibilidad* puede ser uno de los siguientes: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="a9309-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="a9309-142">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="a9309-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="a9309-143">Las implementaciones de propiedad se ejecutan cada vez que se accede a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="a9309-144">Estática y propiedades de la instancia</span><span class="sxs-lookup"><span data-stu-id="a9309-144">Static and Instance Properties</span></span>

<span data-ttu-id="a9309-145">Propiedades pueden ser estáticos o propiedades de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a9309-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="a9309-146">Propiedades estáticas se pueden invocar sin una instancia y se usan para los valores asociados con el tipo, no con objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="a9309-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="a9309-147">Para las propiedades estáticas, omita el identificador automática.</span><span class="sxs-lookup"><span data-stu-id="a9309-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="a9309-148">Self-identifier es necesario para las propiedades de instancia.</span><span class="sxs-lookup"><span data-stu-id="a9309-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="a9309-149">La siguiente definición de propiedad estática se basa en un escenario en el que tiene un campo estático `myStaticValue` que es el almacén de respaldo para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="a9309-150">Las propiedades también pueden ser como una matriz, en cuyo caso se denominan *propiedades indizadas*.</span><span class="sxs-lookup"><span data-stu-id="a9309-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="a9309-151">Para obtener más información, consulte [propiedades indizadas](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a9309-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="a9309-152">Anotación de tipo para propiedades</span><span class="sxs-lookup"><span data-stu-id="a9309-152">Type Annotation for Properties</span></span>

<span data-ttu-id="a9309-153">En muchos casos, el compilador tiene información suficiente para inferir el tipo de una propiedad del tipo de almacén de respaldo, pero puede establecer explícitamente el tipo mediante la adición de una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="a9309-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="a9309-154">Usar propiedad conjunto de descriptores de acceso</span><span class="sxs-lookup"><span data-stu-id="a9309-154">Using Property set Accessors</span></span>

<span data-ttu-id="a9309-155">Puede establecer propiedades que proporcionan `set` descriptores de acceso mediante el uso de la `<-` operador.</span><span class="sxs-lookup"><span data-stu-id="a9309-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="a9309-156">El resultado es **20**.</span><span class="sxs-lookup"><span data-stu-id="a9309-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="a9309-157">Propiedades abstractas</span><span class="sxs-lookup"><span data-stu-id="a9309-157">Abstract Properties</span></span>

<span data-ttu-id="a9309-158">Las propiedades pueden ser abstractas.</span><span class="sxs-lookup"><span data-stu-id="a9309-158">Properties can be abstract.</span></span> <span data-ttu-id="a9309-159">Al igual que con los métodos, `abstract` simplemente significa que hay una distribución virtual asociada a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9309-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="a9309-160">Las propiedades abstractas pueden ser abstractas realmente, es decir, sin una definición de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="a9309-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="a9309-161">Por lo tanto, la clase que contiene esta propiedad es una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="a9309-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="a9309-162">Como alternativa, abstract puede significar que una propiedad es virtual y, en ese caso, una definición debe estar presente en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="a9309-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="a9309-163">Tenga en cuenta que las propiedades abstractas no deben ser privadas, y si un descriptor de acceso es abstracto, el otro también debe ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="a9309-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="a9309-164">Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="a9309-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="a9309-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9309-165">See also</span></span>

- [<span data-ttu-id="a9309-166">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9309-166">Members</span></span>](index.md)
- [<span data-ttu-id="a9309-167">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9309-167">Methods</span></span>](methods.md)
