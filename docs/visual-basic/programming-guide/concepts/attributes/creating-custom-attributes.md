---
title: Crear atributos personalizados
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400699"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="baeaf-102">Creating Custom Attributes (Visual Basic) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="baeaf-102">Creating Custom Attributes (Visual Basic)</span></span>

<span data-ttu-id="baeaf-103">Para crear sus propios atributos personalizados, defina una clase de atributo derivada directa o indirectamente de <xref:System.Attribute>, que agiliza y facilita la identificación de las definiciones de atributos en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="baeaf-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="baeaf-104">Imagínese que desea etiquetar tipos con el nombre del programador que los escribió.</span><span class="sxs-lookup"><span data-stu-id="baeaf-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="baeaf-105">Puede definir una clase de atributos `Author` personalizada:</span><span class="sxs-lookup"><span data-stu-id="baeaf-105">You might define a custom `Author` attribute class:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName
        version = 1.0
    End Sub
End Class
```

<span data-ttu-id="baeaf-106">El nombre de la clase es el nombre del atributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="baeaf-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="baeaf-107">Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizada.</span><span class="sxs-lookup"><span data-stu-id="baeaf-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="baeaf-108">Los parámetros del constructor son los parámetros posicionales del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="baeaf-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="baeaf-109">En este ejemplo, `name` es un parámetro posicional.</span><span class="sxs-lookup"><span data-stu-id="baeaf-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="baeaf-110">Las propiedades o los campos públicos de lectura y escritura son parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="baeaf-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="baeaf-111">En este caso, `version` es el único parámetro con nombre.</span><span class="sxs-lookup"><span data-stu-id="baeaf-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="baeaf-112">Observe el uso del atributo `AttributeUsage` para hacer que el atributo `Author` sea válido solo en las declaraciones de clase y de `Structure`.</span><span class="sxs-lookup"><span data-stu-id="baeaf-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>

<span data-ttu-id="baeaf-113">Puede usar este nuevo atributo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="baeaf-113">You could use this new attribute as follows:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

<span data-ttu-id="baeaf-114">`AttributeUsage` tiene un parámetro con nombre, `AllowMultiple`, con el que puede hacer que un atributo personalizado sea multiuso o de un solo uso.</span><span class="sxs-lookup"><span data-stu-id="baeaf-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="baeaf-115">En el ejemplo de código siguiente se crea un atributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="baeaf-115">In the following code example, a multiuse attribute is created.</span></span>

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

<span data-ttu-id="baeaf-116">En el ejemplo de código siguiente se aplican varios atributos del mismo tipo a una clase.</span><span class="sxs-lookup"><span data-stu-id="baeaf-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> <span data-ttu-id="baeaf-117">Si la clase de atributo contiene una propiedad, dicha propiedad debe ser de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="baeaf-117">If your attribute class contains a property, that property must be read-write.</span></span>

## <a name="see-also"></a><span data-ttu-id="baeaf-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="baeaf-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="baeaf-119">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="baeaf-119">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="baeaf-120">Escribir atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="baeaf-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- <span data-ttu-id="baeaf-121">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="baeaf-121">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="baeaf-122">Atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baeaf-122">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="baeaf-123">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="baeaf-123">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>
- [<span data-ttu-id="baeaf-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baeaf-124">AttributeUsage (Visual Basic)</span></span>](attributeusage.md)
