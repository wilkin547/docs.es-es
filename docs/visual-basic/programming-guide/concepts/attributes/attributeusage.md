---
title: AttributeUsage
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: 677d49aba38801f2adf42cc745983af30b3eddc5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400737"
---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="e2a8e-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2a8e-102">AttributeUsage (Visual Basic)</span></span>

<span data-ttu-id="e2a8e-103">Determina cómo se puede usar una clase de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="e2a8e-104">`AttributeUsage` es un atributo que se puede aplicar a definiciones de atributos personalizados para controlar cómo se aplica el nuevo atributo.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="e2a8e-105">La configuración predeterminada presenta este aspecto cuando se aplica explícitamente:</span><span class="sxs-lookup"><span data-stu-id="e2a8e-105">The default settings look like this when applied explicitly:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

<span data-ttu-id="e2a8e-106">En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier entidad de código atribuible, pero solo se puede aplicar una vez a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="e2a8e-107">Las clases derivadas la heredan cuando se aplica a una clase base.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-107">It is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="e2a8e-108">Los argumentos `AllowMultiple` y `Inherited` son opcionales, por lo que este código tiene el mismo efecto:</span><span class="sxs-lookup"><span data-stu-id="e2a8e-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

<span data-ttu-id="e2a8e-109">El primer argumento `AttributeUsage` debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="e2a8e-110">Se pueden vincular diversos tipos de destino con el operador OR, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="e2a8e-110">Multiple target types can be linked together with the OR operator, like this:</span></span>

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

<span data-ttu-id="e2a8e-111">Si el argumento `AllowMultiple` se establece en `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="e2a8e-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

<span data-ttu-id="e2a8e-112">En este caso, `MultiUseAttr` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="e2a8e-113">Los dos formatos mostrados para aplicar varios atributos son válidos.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-113">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="e2a8e-114">Si `Inherited` se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="e2a8e-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2a8e-115">For example:</span></span>

```vb
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>
Class Attr1
    Inherits Attribute
End Class

<Attr1()>
Class BClass

End Class

Class DClass
    Inherits BClass
End Class
```

<span data-ttu-id="e2a8e-116">En este caso, `Attr1` no se aplica a `DClass` a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2a8e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2a8e-117">Remarks</span></span>

<span data-ttu-id="e2a8e-118">`AttributeUsage` es un atributo de uso único; no se puede aplicar más de una vez a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="e2a8e-119">`AttributeUsage` es un alias de <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="e2a8e-120">Para más información, vea [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="e2a8e-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="e2a8e-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2a8e-121">Example</span></span>

<span data-ttu-id="e2a8e-122">En el ejemplo siguiente se muestra el efecto de los argumentos `Inherited` y `AllowMultiple` en el atributo `AttributeUsage` y cómo se pueden enumerar los atributos personalizados aplicados a una clase.</span><span class="sxs-lookup"><span data-stu-id="e2a8e-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

```vb
' Create some custom attributes:
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>
Class A1
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class)>
Class A2
    Inherits System.Attribute
End Class

<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>
Class A3
    Inherits System.Attribute
End Class

' Apply custom attributes to classes:
<A1(), A2()>
Class BaseClass

End Class

<A3(), A3()>
Class DerivedClass
    Inherits BaseClass
End Class

Public Class TestAttributeUsage
    Sub Main()
        Dim b As New BaseClass
        Dim d As New DerivedClass
        ' Display custom attributes for each class.
        Console.WriteLine("Attributes on Base Class:")
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)

        For Each attr In attrs
            Console.WriteLine(attr)
        Next

        Console.WriteLine("Attributes on Derived Class:")
        attrs = d.GetType().GetCustomAttributes(True)
        For Each attr In attrs
            Console.WriteLine(attr)
        Next
    End Sub
End Class
```

## <a name="sample-output"></a><span data-ttu-id="e2a8e-123">Salida de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2a8e-123">Sample Output</span></span>

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a><span data-ttu-id="e2a8e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2a8e-124">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="e2a8e-125">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2a8e-125">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="e2a8e-126">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2a8e-126">Attributes</span></span>](../../../../standard/attributes/index.md)
- <span data-ttu-id="e2a8e-127">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2a8e-127">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="e2a8e-128">Atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2a8e-128">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="e2a8e-129">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2a8e-129">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md)</span></span>
- <span data-ttu-id="e2a8e-130">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="e2a8e-130">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>
