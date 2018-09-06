---
title: Inherits (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 4a98ada39a04730b46f40fe139e72d1855d9b067
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739508"
---
# <a name="inherits-statement"></a><span data-ttu-id="92dd3-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="92dd3-102">Inherits Statement</span></span>
<span data-ttu-id="92dd3-103">Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="92dd3-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92dd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92dd3-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="92dd3-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="92dd3-105">Parts</span></span>  
  
|<span data-ttu-id="92dd3-106">Término</span><span class="sxs-lookup"><span data-stu-id="92dd3-106">Term</span></span>|<span data-ttu-id="92dd3-107">Definición</span><span class="sxs-lookup"><span data-stu-id="92dd3-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="92dd3-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="92dd3-108">Required.</span></span> <span data-ttu-id="92dd3-109">El nombre de la clase del que se deriva esta clase.</span><span class="sxs-lookup"><span data-stu-id="92dd3-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="92dd3-110">O bien</span><span class="sxs-lookup"><span data-stu-id="92dd3-110">-or-</span></span><br /><br /> <span data-ttu-id="92dd3-111">Los nombres de las interfaces que esta interfaz se deriva.</span><span class="sxs-lookup"><span data-stu-id="92dd3-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="92dd3-112">Use comas para separar varios nombres.</span><span class="sxs-lookup"><span data-stu-id="92dd3-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92dd3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92dd3-113">Remarks</span></span>  
 <span data-ttu-id="92dd3-114">Si usa, la `Inherits` instrucción debe ser la primera línea no vacía, sin comentarios en una definición de clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="92dd3-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="92dd3-115">Debe seguir inmediatamente a la `Class` o `Interface` instrucción.</span><span class="sxs-lookup"><span data-stu-id="92dd3-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="92dd3-116">Puede usar `Inherits` solo en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="92dd3-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="92dd3-117">Esto significa que el contexto de declaración de una herencia no puede ser un archivo de código fuente, espacio de nombres, estructura, módulo, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="92dd3-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="92dd3-118">Reglas</span><span class="sxs-lookup"><span data-stu-id="92dd3-118">Rules</span></span>  
  
-   <span data-ttu-id="92dd3-119">**Herencia de clases.**</span><span class="sxs-lookup"><span data-stu-id="92dd3-119">**Class Inheritance.**</span></span> <span data-ttu-id="92dd3-120">Si una clase utiliza la `Inherits` instrucción, puede especificar sólo una clase base.</span><span class="sxs-lookup"><span data-stu-id="92dd3-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="92dd3-121">Una clase no puede heredar de una clase anidada dentro de él.</span><span class="sxs-lookup"><span data-stu-id="92dd3-121">A class cannot inherit from a class nested within it.</span></span>  
  
-   <span data-ttu-id="92dd3-122">**Herencia de interfaz.**</span><span class="sxs-lookup"><span data-stu-id="92dd3-122">**Interface Inheritance.**</span></span> <span data-ttu-id="92dd3-123">Si usa una interfaz el `Inherits` instrucción, puede especificar una o varias interfaces bases.</span><span class="sxs-lookup"><span data-stu-id="92dd3-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="92dd3-124">Puede heredar de dos interfaces incluso si cada uno de ellos define un miembro con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="92dd3-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="92dd3-125">Si lo hace, el código de implementación debe utilizar la calificación de nombres para especificar qué miembro se implementa.</span><span class="sxs-lookup"><span data-stu-id="92dd3-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="92dd3-126">Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="92dd3-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="92dd3-127">Por ejemplo, un `Public` interfaz no puede heredar de un `Friend` interfaz.</span><span class="sxs-lookup"><span data-stu-id="92dd3-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="92dd3-128">Una interfaz no puede heredar de una interfaz anidada dentro de él.</span><span class="sxs-lookup"><span data-stu-id="92dd3-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="92dd3-129">Un ejemplo de herencia de clases en .NET Framework es la <xref:System.ArgumentException> (clase), que hereda de la <xref:System.SystemException> clase.</span><span class="sxs-lookup"><span data-stu-id="92dd3-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="92dd3-130">Esto proporciona a <xref:System.ArgumentException> todas las propiedades predefinidas y los procedimientos requeridos por las excepciones del sistema, como el <xref:System.Exception.Message%2A> propiedad y el <xref:System.Exception.ToString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="92dd3-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="92dd3-131">Un ejemplo de herencia de interfaz de .NET Framework es la <xref:System.Collections.ICollection> interfaz, que hereda de la <xref:System.Collections.IEnumerable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="92dd3-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="92dd3-132">Esto hace que <xref:System.Collections.ICollection> para heredar la definición del enumerador necesario para recorrer una colección.</span><span class="sxs-lookup"><span data-stu-id="92dd3-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92dd3-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92dd3-133">Example</span></span>  
 <span data-ttu-id="92dd3-134">En el ejemplo siguiente se usa el `Inherits` instrucción para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass`.</span><span class="sxs-lookup"><span data-stu-id="92dd3-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="92dd3-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92dd3-135">Example</span></span>  
 <span data-ttu-id="92dd3-136">El ejemplo siguiente muestra la herencia de varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="92dd3-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 <span data-ttu-id="92dd3-137">La interfaz denominada `thisInterface` ahora incluye todas las definiciones en el <xref:System.IComparable>, <xref:System.IDisposable>, y <xref:System.IFormattable> interfaces de los miembros heredados proporcionan respectivamente para la comparación específico del tipo de dos objetos, liberar recursos asignan y se expresa el valor de un objeto como un `String`.</span><span class="sxs-lookup"><span data-stu-id="92dd3-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="92dd3-138">Una clase que implementa `thisInterface` debe implementar todos los miembros de todas las interfaces base.</span><span class="sxs-lookup"><span data-stu-id="92dd3-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dd3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="92dd3-139">See Also</span></span>  
 [<span data-ttu-id="92dd3-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="92dd3-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [<span data-ttu-id="92dd3-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="92dd3-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="92dd3-142">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="92dd3-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="92dd3-143">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="92dd3-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="92dd3-144">Interfaces</span><span class="sxs-lookup"><span data-stu-id="92dd3-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
