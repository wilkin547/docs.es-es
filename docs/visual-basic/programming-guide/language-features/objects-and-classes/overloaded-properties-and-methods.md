---
title: "Propiedades y métodos sobrecargados (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="47f28-102">Propiedades y métodos sobrecargados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47f28-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="47f28-103">La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumento.</span><span class="sxs-lookup"><span data-stu-id="47f28-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="47f28-104">Uso de la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="47f28-104">Overloading Usage</span></span>  
 <span data-ttu-id="47f28-105">La sobrecarga es especialmente útil cuando el modelo de objeto exige el uso de nombres idénticos para procedimientos que operan en diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="47f28-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="47f28-106">Por ejemplo, podría tener una clase que puede mostrar varios tipos de datos diferentes `Display` procedimientos que tengan un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="47f28-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 <span data-ttu-id="47f28-107">Sin sobrecarga, sería necesario crear nombres distintos para cada procedimiento, aunque lo hacen lo mismo, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="47f28-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 <span data-ttu-id="47f28-108">Sobrecarga resulta más fácil utilizar los métodos o propiedades porque proporciona una opción de tipos de datos que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="47f28-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="47f28-109">Por ejemplo, sobrecargado `Display` método descrito anteriormente puede llamarse con cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="47f28-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 <span data-ttu-id="47f28-110">En tiempo de ejecución [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] llama el procedimiento correcto basándose en los tipos de datos de los parámetros especifique.</span><span class="sxs-lookup"><span data-stu-id="47f28-110">At run time, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="47f28-111">Reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="47f28-111">Overloading Rules</span></span>  
 <span data-ttu-id="47f28-112">Crear a un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="47f28-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="47f28-113">Excepto para los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros y los elementos siguientes no se puede usar como una característica distintiva al sobrecargar una propiedad o procedimiento:</span><span class="sxs-lookup"><span data-stu-id="47f28-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="47f28-114">Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o parámetros del miembro.</span><span class="sxs-lookup"><span data-stu-id="47f28-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="47f28-115">Nombres de parámetros</span><span class="sxs-lookup"><span data-stu-id="47f28-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="47f28-116">Tipos de valor devueltos de procedimientos</span><span class="sxs-lookup"><span data-stu-id="47f28-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="47f28-117">El `Overloads` palabra clave es opcional cuando sobrecargue un procedimiento, pero si alguna sobrecarga miembro usa la `Overloads` palabra clave y, a continuación, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="47f28-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="47f28-118">Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tengan idénticos parámetros y tipos de parámetros, un proceso conocido como *sombrear por nombre y firma*.</span><span class="sxs-lookup"><span data-stu-id="47f28-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="47f28-119">Si el `Overloads` se utiliza la palabra clave cuando sombrear por nombre y firma, implementación de la clase derivada del miembro se usará en lugar de la implementación de la clase base y todas las demás sobrecargas de dicho miembro estarán disponibles para instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="47f28-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="47f28-120">Si el `Overloads` se omite la palabra clave al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, a continuación, la sobrecarga se denomina *sombrear por nombre*.</span><span class="sxs-lookup"><span data-stu-id="47f28-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="47f28-121">Sombrear por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas disponibles para las instancias de la clase derivada y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="47f28-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="47f28-122">El `Overloads` y `Shadows` modificadores no pueden utilizarse con la misma propiedad o método.</span><span class="sxs-lookup"><span data-stu-id="47f28-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="47f28-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47f28-123">Example</span></span>  
 <span data-ttu-id="47f28-124">El ejemplo siguiente crea métodos sobrecargados que aceptan un `String` o `Decimal` representación de una cantidad en dólares y devuelven una cadena que contiene los impuestos.</span><span class="sxs-lookup"><span data-stu-id="47f28-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="47f28-125">Para usar este ejemplo para crear un método sobrecargado</span><span class="sxs-lookup"><span data-stu-id="47f28-125">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="47f28-126">Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="47f28-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="47f28-127">Agregue el código siguiente a la clase `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="47f28-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  <span data-ttu-id="47f28-128">Agregue el siguiente procedimiento para el formulario.</span><span class="sxs-lookup"><span data-stu-id="47f28-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  <span data-ttu-id="47f28-129">Agregar un botón a su formulario y llame a la `ShowTax` procedimiento desde la `Button1_Click` eventos del botón.</span><span class="sxs-lookup"><span data-stu-id="47f28-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="47f28-130">Ejecute el proyecto y haga clic en el botón del formulario para probar sobrecargado `ShowTax` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="47f28-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="47f28-131">En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="47f28-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="47f28-132">Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "precio es una cadena.</span><span class="sxs-lookup"><span data-stu-id="47f28-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="47f28-133">Impuestos es $5.12" se muestra.</span><span class="sxs-lookup"><span data-stu-id="47f28-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="47f28-134">`TaxAmount`se llama con un `Decimal` valor de la segunda vez y el mensaje, "Price is a Decimal.</span><span class="sxs-lookup"><span data-stu-id="47f28-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="47f28-135">Impuestos es $5.12" se muestra.</span><span class="sxs-lookup"><span data-stu-id="47f28-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f28-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="47f28-136">See Also</span></span>  
 [<span data-ttu-id="47f28-137">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="47f28-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="47f28-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47f28-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="47f28-139">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47f28-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="47f28-140">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="47f28-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="47f28-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="47f28-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="47f28-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="47f28-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="47f28-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="47f28-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="47f28-144">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="47f28-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="47f28-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="47f28-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
