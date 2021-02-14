---
description: 'Más información acerca de: definición de tipo anónimo (Visual Basic)'
title: Definición de tipo anónimo
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 2e3f847f5f844e3ed6e036c26efc330a237d193f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436921"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="a744a-103">Definición de tipos anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a744a-103">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="a744a-104">En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas para el tipo.</span><span class="sxs-lookup"><span data-stu-id="a744a-104">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="a744a-105">Código de Compiler-Generated</span><span class="sxs-lookup"><span data-stu-id="a744a-105">Compiler-Generated Code</span></span>

<span data-ttu-id="a744a-106">En la siguiente definición de `product` , el compilador crea una nueva definición de clase que contiene las propiedades `Name` , `Price` y `OnHand` .</span><span class="sxs-lookup"><span data-stu-id="a744a-106">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="a744a-107">La definición de clase contiene definiciones de propiedades similares a las siguientes.</span><span class="sxs-lookup"><span data-stu-id="a744a-107">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="a744a-108">Observe que no hay ningún `Set` método para las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="a744a-108">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="a744a-109">Los valores de las propiedades de clave son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a744a-109">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="a744a-110">Además, las definiciones de tipos anónimos contienen un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="a744a-110">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="a744a-111">No se permiten constructores que requieran parámetros.</span><span class="sxs-lookup"><span data-stu-id="a744a-111">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="a744a-112">Si una declaración de tipos anónimos contiene al menos una propiedad de clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="a744a-112">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="a744a-113">Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se invalida.</span><span class="sxs-lookup"><span data-stu-id="a744a-113">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="a744a-114">Las invalidaciones proporcionan la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="a744a-114">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="a744a-115">`Equals` Devuelve `True` si dos instancias de tipo anónimo son la misma instancia, o si cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a744a-115">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="a744a-116">Tienen el mismo número de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a744a-116">They have the same number of properties.</span></span>

  - <span data-ttu-id="a744a-117">Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos.</span><span class="sxs-lookup"><span data-stu-id="a744a-117">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="a744a-118">Las comparaciones de nombres no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a744a-118">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="a744a-119">Al menos una de las propiedades es una propiedad de clave y la `Key` palabra clave se aplica a las mismas propiedades.</span><span class="sxs-lookup"><span data-stu-id="a744a-119">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="a744a-120">La comparación de cada par correspondiente de propiedades de clave devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="a744a-120">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="a744a-121">Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` solo para `employee01` y `employee08` .</span><span class="sxs-lookup"><span data-stu-id="a744a-121">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="a744a-122">El comentario antes de cada línea especifica el motivo por el que la nueva instancia no coincide `employee01` .</span><span class="sxs-lookup"><span data-stu-id="a744a-122">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="a744a-123">`GetHashcode` proporciona un algoritmo GetHashCode único y adecuado.</span><span class="sxs-lookup"><span data-stu-id="a744a-123">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="a744a-124">El algoritmo solo usa las propiedades de clave para calcular el código hash.</span><span class="sxs-lookup"><span data-stu-id="a744a-124">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="a744a-125">`ToString` Devuelve una cadena de valores de propiedad concatenados, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a744a-125">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="a744a-126">Se incluyen las propiedades de clave y no clave.</span><span class="sxs-lookup"><span data-stu-id="a744a-126">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="a744a-127">Las propiedades con nombre explícito de un tipo anónimo no pueden entrar en conflicto con estos métodos generados.</span><span class="sxs-lookup"><span data-stu-id="a744a-127">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="a744a-128">Es decir, no puede utilizar `.Equals` , `.GetHashCode` o `.ToString` para asignar un nombre a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a744a-128">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="a744a-129">Las definiciones de tipos anónimos que incluyen al menos una propiedad de clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="a744a-129">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="a744a-130">Las declaraciones de tipos anónimos crean el mismo tipo anónimo solo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos inferidos, las propiedades se declaran en el mismo orden y las mismas propiedades se marcan como propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="a744a-130">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="a744a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a744a-131">See also</span></span>

- [<span data-ttu-id="a744a-132">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="a744a-132">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="a744a-133">Procedimiento para deducir tipos y nombres de propiedades en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="a744a-133">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
