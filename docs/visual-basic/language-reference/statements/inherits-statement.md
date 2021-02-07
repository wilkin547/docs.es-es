---
description: 'Más información acerca de: Inherits (instrucción)'
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: fba574ec207b384c1e7219341526a4a89c8a619c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768927"
---
# <a name="inherits-statement"></a><span data-ttu-id="d589a-103">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="d589a-103">Inherits Statement</span></span>

<span data-ttu-id="d589a-104">Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="d589a-104">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d589a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d589a-105">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="d589a-106">Partes</span><span class="sxs-lookup"><span data-stu-id="d589a-106">Parts</span></span>  
  
|<span data-ttu-id="d589a-107">Término</span><span class="sxs-lookup"><span data-stu-id="d589a-107">Term</span></span>|<span data-ttu-id="d589a-108">Definición</span><span class="sxs-lookup"><span data-stu-id="d589a-108">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="d589a-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d589a-109">Required.</span></span> <span data-ttu-id="d589a-110">Nombre de la clase de la que se deriva esta clase.</span><span class="sxs-lookup"><span data-stu-id="d589a-110">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="d589a-111">o bien</span><span class="sxs-lookup"><span data-stu-id="d589a-111">-or-</span></span><br /><br /> <span data-ttu-id="d589a-112">Los nombres de las interfaces de las que se deriva esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="d589a-112">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="d589a-113">Use comas para separar varios nombres.</span><span class="sxs-lookup"><span data-stu-id="d589a-113">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d589a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d589a-114">Remarks</span></span>  

 <span data-ttu-id="d589a-115">Si se utiliza, la `Inherits` instrucción debe ser la primera línea no vacía sin comentarios en una definición de clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="d589a-115">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="d589a-116">Debe seguir inmediatamente a la `Class` `Interface` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="d589a-116">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="d589a-117">Solo se puede usar `Inherits` en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="d589a-117">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="d589a-118">Esto significa que el contexto de la declaración de una herencia no puede ser un archivo de código fuente, un espacio de nombres, una estructura, un módulo, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="d589a-118">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d589a-119">Reglas</span><span class="sxs-lookup"><span data-stu-id="d589a-119">Rules</span></span>  
  
- <span data-ttu-id="d589a-120">**Herencia de clases.**</span><span class="sxs-lookup"><span data-stu-id="d589a-120">**Class Inheritance.**</span></span> <span data-ttu-id="d589a-121">Si una clase utiliza la `Inherits` instrucción, solo puede especificar una clase base.</span><span class="sxs-lookup"><span data-stu-id="d589a-121">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="d589a-122">Una clase no puede heredar de una clase anidada dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="d589a-122">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="d589a-123">**Herencia de interfaz.**</span><span class="sxs-lookup"><span data-stu-id="d589a-123">**Interface Inheritance.**</span></span> <span data-ttu-id="d589a-124">Si una interfaz utiliza la `Inherits` instrucción, puede especificar una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="d589a-124">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="d589a-125">Puede heredar de dos interfaces incluso si cada una de ellas define un miembro con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="d589a-125">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="d589a-126">Si lo hace, el código de implementación debe usar la calificación de nombre para especificar qué miembro está implementando.</span><span class="sxs-lookup"><span data-stu-id="d589a-126">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="d589a-127">Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="d589a-127">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="d589a-128">Por ejemplo, una `Public` interfaz no puede heredar de una `Friend` interfaz.</span><span class="sxs-lookup"><span data-stu-id="d589a-128">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="d589a-129">Una interfaz no puede heredar de una interfaz anidada dentro de ella.</span><span class="sxs-lookup"><span data-stu-id="d589a-129">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="d589a-130">Un ejemplo de herencia de clases en el .NET Framework es la <xref:System.ArgumentException> clase, que hereda de la <xref:System.SystemException> clase.</span><span class="sxs-lookup"><span data-stu-id="d589a-130">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="d589a-131">Esto proporciona a <xref:System.ArgumentException> todas las propiedades y los procedimientos predefinidos que requieren las excepciones del sistema, como la <xref:System.Exception.Message%2A> propiedad y el <xref:System.Exception.ToString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d589a-131">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="d589a-132">Un ejemplo de herencia de interfaz en el .NET Framework es la <xref:System.Collections.ICollection> interfaz, que hereda de la <xref:System.Collections.IEnumerable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="d589a-132">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="d589a-133">Esto hace que <xref:System.Collections.ICollection> herede la definición del enumerador necesaria para atravesar una colección.</span><span class="sxs-lookup"><span data-stu-id="d589a-133">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d589a-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d589a-134">Example</span></span>  

 <span data-ttu-id="d589a-135">En el ejemplo siguiente se usa la `Inherits` instrucción para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass` .</span><span class="sxs-lookup"><span data-stu-id="d589a-135">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="d589a-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d589a-136">Example</span></span>  

 <span data-ttu-id="d589a-137">En el ejemplo siguiente se muestra la herencia de varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="d589a-137">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="d589a-138">La interfaz denominada `thisInterface` ahora incluye todas las definiciones de las <xref:System.IComparable> <xref:System.IDisposable> interfaces, y <xref:System.IFormattable> que los miembros heredados proporcionan respectivamente para la comparación específica del tipo de dos objetos, liberando los recursos asignados y expresando el valor de un objeto como `String` .</span><span class="sxs-lookup"><span data-stu-id="d589a-138">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="d589a-139">Una clase que implementa `thisInterface` debe implementar todos los miembros de cada interfaz base.</span><span class="sxs-lookup"><span data-stu-id="d589a-139">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d589a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d589a-140">See also</span></span>

- [<span data-ttu-id="d589a-141">MustInherit</span><span class="sxs-lookup"><span data-stu-id="d589a-141">MustInherit</span></span>](../modifiers/mustinherit.md)
- [<span data-ttu-id="d589a-142">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="d589a-142">NotInheritable</span></span>](../modifiers/notinheritable.md)
- [<span data-ttu-id="d589a-143">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="d589a-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="d589a-144">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="d589a-144">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="d589a-145">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d589a-145">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
