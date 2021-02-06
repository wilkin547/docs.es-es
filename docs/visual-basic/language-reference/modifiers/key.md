---
description: 'Más información acerca de: clave (Visual Basic)'
title: Clave
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 5ec918da661144053824ca2a734cdec11873b0e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640802"
---
# <a name="key-visual-basic"></a><span data-ttu-id="e2756-103">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2756-103">Key (Visual Basic)</span></span>

<span data-ttu-id="e2756-104">La `Key` palabra clave le permite especificar el comportamiento de las propiedades de los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="e2756-104">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="e2756-105">Solo las propiedades que se designan como propiedades clave participan en las pruebas de igualdad entre las instancias de tipo anónimo o el cálculo de los valores de código hash.</span><span class="sxs-lookup"><span data-stu-id="e2756-105">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="e2756-106">No se pueden cambiar los valores de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="e2756-106">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="e2756-107">Designe una propiedad de un tipo anónimo como una propiedad de clave colocando la palabra clave `Key` delante de su declaración en la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e2756-107">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="e2756-108">En el ejemplo siguiente, `Airline` y `FlightNo` son propiedades clave, pero `Gate` no lo es.</span><span class="sxs-lookup"><span data-stu-id="e2756-108">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="e2756-109">Cuando se crea un nuevo tipo anónimo, hereda directamente de <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="e2756-109">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="e2756-110">El compilador invalida tres miembros heredados: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="e2756-110">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="e2756-111">El código de invalidación que se produce para <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> se basa en las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="e2756-111">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="e2756-112">Si no hay ninguna propiedad clave en el tipo, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.Equals%2A> no se reemplazan.</span><span class="sxs-lookup"><span data-stu-id="e2756-112">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="e2756-113">Igualdad</span><span class="sxs-lookup"><span data-stu-id="e2756-113">Equality</span></span>  

 <span data-ttu-id="e2756-114">Dos instancias de tipo anónimo son iguales si son instancias del mismo tipo y si los valores de sus propiedades de clave son iguales.</span><span class="sxs-lookup"><span data-stu-id="e2756-114">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="e2756-115">En los ejemplos siguientes, `flight2` es igual a `flight1` en el ejemplo anterior porque son instancias del mismo tipo anónimo y tienen valores coincidentes para sus propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="e2756-115">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="e2756-116">Sin embargo, `flight3` no es igual a `flight1` porque tiene un valor diferente para una propiedad de clave, `FlightNo` .</span><span class="sxs-lookup"><span data-stu-id="e2756-116">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="e2756-117">`flight4`La instancia no es del mismo tipo que `flight1` porque designan propiedades diferentes como propiedades clave.</span><span class="sxs-lookup"><span data-stu-id="e2756-117">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="e2756-118">Si dos instancias de se declaran solo con propiedades que no son de clave, idénticas en nombre, tipo, orden y valor, las dos instancias de no son iguales.</span><span class="sxs-lookup"><span data-stu-id="e2756-118">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="e2756-119">Una instancia sin propiedades de clave es igual a sí misma.</span><span class="sxs-lookup"><span data-stu-id="e2756-119">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="e2756-120">Para obtener más información sobre las condiciones en las que dos instancias de tipos anónimos son instancias del mismo tipo anónimo, vea [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="e2756-120">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="e2756-121">Cálculo de código hash</span><span class="sxs-lookup"><span data-stu-id="e2756-121">Hash Code Calculation</span></span>  

 <span data-ttu-id="e2756-122">Al igual <xref:System.Object.Equals%2A> que, la función hash que se define en <xref:System.Object.GetHashCode%2A> para un tipo anónimo se basa en las propiedades clave del tipo.</span><span class="sxs-lookup"><span data-stu-id="e2756-122">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="e2756-123">En los siguientes ejemplos se muestra la interacción entre las propiedades de clave y los valores de código hash.</span><span class="sxs-lookup"><span data-stu-id="e2756-123">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="e2756-124">Las instancias de un tipo anónimo que tienen los mismos valores para todas las propiedades de clave tienen el mismo valor de código hash, incluso si las propiedades que no son de clave no tienen valores coincidentes.</span><span class="sxs-lookup"><span data-stu-id="e2756-124">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="e2756-125">La siguiente instrucción devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="e2756-125">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="e2756-126">Las instancias de un tipo anónimo que tienen valores diferentes para una o varias propiedades de clave tienen diferentes valores de código hash.</span><span class="sxs-lookup"><span data-stu-id="e2756-126">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="e2756-127">La siguiente instrucción devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="e2756-127">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="e2756-128">Las instancias de tipos anónimos que designan propiedades diferentes como propiedades clave no son instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e2756-128">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="e2756-129">Tienen valores de código hash diferentes incluso cuando los nombres y valores de todas las propiedades son iguales.</span><span class="sxs-lookup"><span data-stu-id="e2756-129">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="e2756-130">La siguiente instrucción devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="e2756-130">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="e2756-131">Read-Only valores</span><span class="sxs-lookup"><span data-stu-id="e2756-131">Read-Only Values</span></span>  

 <span data-ttu-id="e2756-132">No se pueden cambiar los valores de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="e2756-132">The values of key properties cannot be changed.</span></span> <span data-ttu-id="e2756-133">Por ejemplo, en `flight1` los ejemplos anteriores, los `Airline` campos y `FlightNo` son de solo lectura, pero `Gate` se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="e2756-133">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e2756-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2756-134">See also</span></span>

- [<span data-ttu-id="e2756-135">Definición de tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="e2756-135">Anonymous Type Definition</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="e2756-136">Procedimiento para deducir tipos y nombres de propiedades en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="e2756-136">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="e2756-137">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="e2756-137">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
