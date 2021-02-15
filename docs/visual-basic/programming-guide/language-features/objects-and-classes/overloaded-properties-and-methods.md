---
description: 'Más información sobre: propiedades y métodos sobrecargados (Visual Basic)'
title: Propiedades y métodos sobrecargados
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: fb46876d346ad5f391241aee0b07175df290e656
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438780"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="b7b0f-103">Propiedades y métodos sobrecargados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7b0f-103">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="b7b0f-104">La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-104">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="b7b0f-105">Sobrecarga del uso</span><span class="sxs-lookup"><span data-stu-id="b7b0f-105">Overloading usage</span></span>

<span data-ttu-id="b7b0f-106">La sobrecarga es especialmente útil cuando el modelo de objetos determina que se emplean nombres idénticos para los procedimientos que operan en tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-106">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="b7b0f-107">Por ejemplo, una clase que puede mostrar varios tipos de datos diferentes podría tener `Display` procedimientos que tienen el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b7b0f-107">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="b7b0f-108">Sin sobrecarga, tendría que crear nombres distintos para cada procedimiento, aunque hagan lo mismo, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="b7b0f-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="b7b0f-109">La sobrecarga facilita el uso de propiedades o métodos, ya que proporciona una selección de tipos de datos que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-109">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="b7b0f-110">Por ejemplo, `Display` se puede llamar al método sobrecargado descrito anteriormente con cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="b7b0f-110">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="b7b0f-111">En tiempo de ejecución, Visual Basic llama al procedimiento correcto en función de los tipos de datos de los parámetros que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-111">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="b7b0f-112">Sobrecargar reglas</span><span class="sxs-lookup"><span data-stu-id="b7b0f-112">Overloading rules</span></span>

 <span data-ttu-id="b7b0f-113">Puede crear un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-113">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="b7b0f-114">A excepción de los miembros derivados sobrecargados, cada miembro sobrecargado debe tener listas de parámetros diferentes y los elementos siguientes no se pueden usar como una característica diferenciada al sobrecargar una propiedad o un procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b7b0f-114">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="b7b0f-115">Modificadores, como `ByVal` o `ByRef` , que se aplican a un miembro o a los parámetros del miembro.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-115">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="b7b0f-116">Nombres de parámetros</span><span class="sxs-lookup"><span data-stu-id="b7b0f-116">Names of parameters</span></span>

- <span data-ttu-id="b7b0f-117">Tipos devueltos de procedimientos</span><span class="sxs-lookup"><span data-stu-id="b7b0f-117">Return types of procedures</span></span>

<span data-ttu-id="b7b0f-118">La `Overloads` palabra clave es opcional al sobrecargar, pero si cualquier miembro sobrecargado utiliza la `Overloads` palabra clave, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-118">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="b7b0f-119">Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tienen parámetros y tipos de parámetro idénticos, un proceso conocido como *sombreado por nombre y firma*.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-119">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="b7b0f-120">Si `Overloads` se usa la palabra clave al sombrear por nombre y firma, se usará la implementación de la clase derivada del miembro en lugar de la implementación en la clase base, y todas las demás sobrecargas para ese miembro estarán disponibles para las instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-120">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="b7b0f-121">Si `Overloads` se omite la palabra clave al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, la sobrecarga se denomina *sombreado por nombre*.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-121">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="b7b0f-122">El sombreado por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas no estén disponibles para las instancias de la clase derivada y su decedents.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-122">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="b7b0f-123">Los `Overloads` `Shadows` modificadores y no se pueden usar con la misma propiedad o método.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-123">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="b7b0f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7b0f-124">Example</span></span>

<span data-ttu-id="b7b0f-125">En el ejemplo siguiente se crean métodos sobrecargados que aceptan `String` una `Decimal` representación o de una cantidad de dólares y devuelven una cadena que contiene el impuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-125">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="b7b0f-126">Para usar este ejemplo para crear un método sobrecargado</span><span class="sxs-lookup"><span data-stu-id="b7b0f-126">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="b7b0f-127">Abra un nuevo proyecto y agregue una clase denominada `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="b7b0f-127">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="b7b0f-128">Agregue el siguiente código a la clase `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="b7b0f-128">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="b7b0f-129">Agregue el procedimiento siguiente al formulario.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-129">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="b7b0f-130">Agregue un botón al formulario y llame al `ShowTax` procedimiento desde el `Button1_Click` evento del botón.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-130">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="b7b0f-131">Ejecute el proyecto y haga clic en el botón del formulario para probar el procedimiento sobrecargado `ShowTax` .</span><span class="sxs-lookup"><span data-stu-id="b7b0f-131">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="b7b0f-132">En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincide con los parámetros que se usan.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-132">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="b7b0f-133">Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "Price Is a String.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-133">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="b7b0f-134">Tax es $5,12.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-134">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="b7b0f-135">`TaxAmount` se llama a con un `Decimal` valor la segunda vez y el mensaje, "Price es un decimal.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-135">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="b7b0f-136">Tax es $5,12.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-136">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7b0f-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7b0f-137">See also</span></span>

- [<span data-ttu-id="b7b0f-138">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="b7b0f-138">Objects and Classes</span></span>](index.md)
- [<span data-ttu-id="b7b0f-139">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7b0f-139">Shadowing in Visual Basic</span></span>](../declared-elements/shadowing.md)
- [<span data-ttu-id="b7b0f-140">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="b7b0f-140">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="b7b0f-141">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="b7b0f-141">Inheritance Basics</span></span>](inheritance-basics.md)
- [<span data-ttu-id="b7b0f-142">Shadows</span><span class="sxs-lookup"><span data-stu-id="b7b0f-142">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="b7b0f-143">ByVal</span><span class="sxs-lookup"><span data-stu-id="b7b0f-143">ByVal</span></span>](../../../language-reference/modifiers/byval.md)
- [<span data-ttu-id="b7b0f-144">ByRef</span><span class="sxs-lookup"><span data-stu-id="b7b0f-144">ByRef</span></span>](../../../language-reference/modifiers/byref.md)
- [<span data-ttu-id="b7b0f-145">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="b7b0f-145">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="b7b0f-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="b7b0f-146">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
