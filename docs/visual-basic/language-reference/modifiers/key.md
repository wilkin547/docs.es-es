---
title: Key (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a><span data-ttu-id="1877d-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1877d-102">Key (Visual Basic)</span></span>
<span data-ttu-id="1877d-103">El `Key` (palabra clave) le permite especificar el comportamiento de las propiedades de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="1877d-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="1877d-104">Solo las propiedades se designa como propiedades clave participan en las pruebas de igualdad entre las instancias de tipo anónimo, o un cálculo de valores de código hash.</span><span class="sxs-lookup"><span data-stu-id="1877d-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="1877d-105">No se puede cambiar los valores de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="1877d-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="1877d-106">Para designar una propiedad de un tipo anónimo como propiedad clave colocando la palabra clave `Key` delante de su declaración en la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="1877d-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="1877d-107">En el ejemplo siguiente, `Airline` y `FlightNo` son propiedades de clave, pero `Gate` no es.</span><span class="sxs-lookup"><span data-stu-id="1877d-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 <span data-ttu-id="1877d-108">Cuando se crea un nuevo tipo anónimo, hereda directamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1877d-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="1877d-109">El compilador invalida tres miembros heredados: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1877d-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="1877d-110">El código de invalidación que se genera para <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> se basa en las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="1877d-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="1877d-111">Si no hay ninguna propiedad clave en el tipo, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.Equals%2A> no se reemplaza.</span><span class="sxs-lookup"><span data-stu-id="1877d-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="1877d-112">Igualdad</span><span class="sxs-lookup"><span data-stu-id="1877d-112">Equality</span></span>  
 <span data-ttu-id="1877d-113">Dos instancias de tipo anónimo son iguales si son instancias del mismo tipo y si los valores de sus propiedades claves son iguales.</span><span class="sxs-lookup"><span data-stu-id="1877d-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="1877d-114">En los ejemplos siguientes, `flight2` es igual a `flight1` del ejemplo anterior porque son instancias del mismo anónimo tipo y tengan valores coincidentes para sus propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="1877d-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="1877d-115">Sin embargo, `flight3` no es igual a `flight1` porque tiene un valor diferente para una propiedad clave, `FlightNo`.</span><span class="sxs-lookup"><span data-stu-id="1877d-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="1877d-116">Instancia `flight4` no es del mismo tipo como `flight1` porque designan propiedades diferentes como propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="1877d-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 <span data-ttu-id="1877d-117">Si dos instancias se declaran con sólo clave no propiedades, idénticas en nombre, tipo, orden y valor, las dos instancias no son iguales.</span><span class="sxs-lookup"><span data-stu-id="1877d-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="1877d-118">Una instancia sin propiedades de clave es igual solo a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="1877d-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="1877d-119">Para obtener más información acerca de las condiciones en las que dos instancias de tipo anónimo son instancias del mismo tipo anónimo, vea [tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="1877d-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="1877d-120">Cálculo del código hash</span><span class="sxs-lookup"><span data-stu-id="1877d-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="1877d-121">Al igual que <xref:System.Object.Equals%2A>, la función hash que se define en <xref:System.Object.GetHashCode%2A> para un tipo anónimo se basa en las propiedades claves del tipo.</span><span class="sxs-lookup"><span data-stu-id="1877d-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="1877d-122">Los ejemplos siguientes muestran la interacción entre las propiedades de clave y el hash de valores de código.</span><span class="sxs-lookup"><span data-stu-id="1877d-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="1877d-123">Instancias de un tipo anónimo que tienen los mismos valores para todas las propiedades claves tienen el mismo valor de código hash, aun cuando no sean clave propiedades no tienen valores coincidentes.</span><span class="sxs-lookup"><span data-stu-id="1877d-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="1877d-124">La siguiente instrucción devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="1877d-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 <span data-ttu-id="1877d-125">Instancias de un tipo anónimo que tienen valores diferentes para uno o más propiedades de clave tienen valores de código hash diferente.</span><span class="sxs-lookup"><span data-stu-id="1877d-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="1877d-126">La siguiente instrucción devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="1877d-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 <span data-ttu-id="1877d-127">Instancias de tipos anónimos que designan propiedades diferentes como propiedades de clave no son instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="1877d-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="1877d-128">Tienen valores de código hash diferentes aunque los nombres y valores de todas las propiedades son iguales.</span><span class="sxs-lookup"><span data-stu-id="1877d-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="1877d-129">La siguiente instrucción devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="1877d-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a><span data-ttu-id="1877d-130">Valores de solo lectura</span><span class="sxs-lookup"><span data-stu-id="1877d-130">Read-Only Values</span></span>  
 <span data-ttu-id="1877d-131">No se puede cambiar los valores de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="1877d-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="1877d-132">Por ejemplo, en `flight1` en los ejemplos anteriores, la `Airline` y `FlightNo` campos son de solo lectura, pero `Gate` puede cambiarse.</span><span class="sxs-lookup"><span data-stu-id="1877d-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1877d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1877d-133">See Also</span></span>  
 [<span data-ttu-id="1877d-134">Definición de tipo anónimo</span><span class="sxs-lookup"><span data-stu-id="1877d-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [<span data-ttu-id="1877d-135">Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="1877d-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [<span data-ttu-id="1877d-136">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="1877d-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
