---
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
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346088"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="ea24b-102">Propiedades y métodos sobrecargados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea24b-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="ea24b-103">La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ea24b-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="ea24b-104">Sobrecarga del uso</span><span class="sxs-lookup"><span data-stu-id="ea24b-104">Overloading usage</span></span>

<span data-ttu-id="ea24b-105">La sobrecarga es especialmente útil cuando el modelo de objetos determina que se emplean nombres idénticos para los procedimientos que operan en tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ea24b-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="ea24b-106">Por ejemplo, una clase que puede mostrar varios tipos de datos diferentes podría tener `Display` procedimientos que tienen el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="ea24b-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="ea24b-107">Sin sobrecarga, tendría que crear nombres distintos para cada procedimiento, aunque hagan lo mismo, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="ea24b-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="ea24b-108">La sobrecarga facilita el uso de propiedades o métodos, ya que proporciona una selección de tipos de datos que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="ea24b-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="ea24b-109">Por ejemplo, se puede llamar al método sobrecargado `Display` descrito anteriormente con cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="ea24b-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="ea24b-110">En tiempo de ejecución, Visual Basic llama al procedimiento correcto en función de los tipos de datos de los parámetros que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="ea24b-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="ea24b-111">Sobrecargar reglas</span><span class="sxs-lookup"><span data-stu-id="ea24b-111">Overloading rules</span></span>

 <span data-ttu-id="ea24b-112">Puede crear un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ea24b-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="ea24b-113">A excepción de los miembros derivados sobrecargados, cada miembro sobrecargado debe tener listas de parámetros diferentes y los elementos siguientes no se pueden usar como una característica diferenciada al sobrecargar una propiedad o un procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ea24b-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="ea24b-114">Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o a los parámetros del miembro.</span><span class="sxs-lookup"><span data-stu-id="ea24b-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="ea24b-115">Nombres de parámetros</span><span class="sxs-lookup"><span data-stu-id="ea24b-115">Names of parameters</span></span>

- <span data-ttu-id="ea24b-116">Tipos devueltos de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ea24b-116">Return types of procedures</span></span>

<span data-ttu-id="ea24b-117">La palabra clave `Overloads` es opcional al sobrecargar, pero si cualquier miembro sobrecargado utiliza la palabra clave `Overloads`, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ea24b-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="ea24b-118">Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tienen parámetros y tipos de parámetro idénticos, un proceso conocido como *sombreado por nombre y firma*.</span><span class="sxs-lookup"><span data-stu-id="ea24b-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="ea24b-119">Si se usa la palabra clave `Overloads` al sombrear por nombre y firma, se usará la implementación de la clase derivada del miembro en lugar de la implementación en la clase base, y todas las demás sobrecargas para ese miembro estarán disponibles para las instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ea24b-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="ea24b-120">Si se omite la palabra clave `Overloads` al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, la sobrecarga se denomina *sombreado por nombre*.</span><span class="sxs-lookup"><span data-stu-id="ea24b-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="ea24b-121">El sombreado por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas no estén disponibles para las instancias de la clase derivada y su decedents.</span><span class="sxs-lookup"><span data-stu-id="ea24b-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="ea24b-122">Los modificadores `Overloads` y `Shadows` no se pueden usar con la misma propiedad o método.</span><span class="sxs-lookup"><span data-stu-id="ea24b-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="ea24b-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea24b-123">Example</span></span>

<span data-ttu-id="ea24b-124">En el ejemplo siguiente se crean métodos sobrecargados que aceptan una representación `String` o `Decimal` de una cantidad de dólares y devuelven una cadena que contiene el impuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="ea24b-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="ea24b-125">Para usar este ejemplo para crear un método sobrecargado</span><span class="sxs-lookup"><span data-stu-id="ea24b-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="ea24b-126">Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="ea24b-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="ea24b-127">Agregue el código siguiente a la clase `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="ea24b-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="ea24b-128">Agregue el procedimiento siguiente al formulario.</span><span class="sxs-lookup"><span data-stu-id="ea24b-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="ea24b-129">Agregue un botón al formulario y llame al procedimiento `ShowTax` desde el evento `Button1_Click` del botón.</span><span class="sxs-lookup"><span data-stu-id="ea24b-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="ea24b-130">Ejecute el proyecto y haga clic en el botón del formulario para probar el procedimiento sobrecargado `ShowTax`.</span><span class="sxs-lookup"><span data-stu-id="ea24b-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="ea24b-131">En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincide con los parámetros que se usan.</span><span class="sxs-lookup"><span data-stu-id="ea24b-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="ea24b-132">Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje "Price Is a String.</span><span class="sxs-lookup"><span data-stu-id="ea24b-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="ea24b-133">Tax es $5,12.</span><span class="sxs-lookup"><span data-stu-id="ea24b-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="ea24b-134">`TaxAmount` se llama con un valor `Decimal` la segunda vez y el mensaje, "Price es un decimal.</span><span class="sxs-lookup"><span data-stu-id="ea24b-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="ea24b-135">Tax es $5,12.</span><span class="sxs-lookup"><span data-stu-id="ea24b-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea24b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea24b-136">See also</span></span>

- [<span data-ttu-id="ea24b-137">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="ea24b-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="ea24b-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea24b-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="ea24b-139">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ea24b-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ea24b-140">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="ea24b-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="ea24b-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="ea24b-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ea24b-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="ea24b-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="ea24b-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="ea24b-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="ea24b-144">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="ea24b-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="ea24b-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="ea24b-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
