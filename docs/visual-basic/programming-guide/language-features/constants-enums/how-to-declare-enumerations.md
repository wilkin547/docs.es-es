---
description: 'Más información acerca de cómo: declarar enumeraciones (Visual Basic)'
title: Procedimiento para declarar enumeraciones
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 10ce0b16a03b832c5afed4d7a310ffb729338e57
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471635"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="acc9c-103">Cómo: Declarar enumeraciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acc9c-103">How to: Declare Enumerations (Visual Basic)</span></span>

<span data-ttu-id="acc9c-104">Cree una enumeración con la `Enum` instrucción en la sección de declaraciones de una clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="acc9c-104">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="acc9c-105">No se puede declarar una enumeración dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="acc9c-105">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="acc9c-106">Para especificar el nivel de acceso adecuado, use `Private` , `Protected` , `Friend` o `Public` .</span><span class="sxs-lookup"><span data-stu-id="acc9c-106">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="acc9c-107">Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante.</span><span class="sxs-lookup"><span data-stu-id="acc9c-107">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="acc9c-108">El nombre debe ser un calificador de .NET Visual Basic válido.</span><span class="sxs-lookup"><span data-stu-id="acc9c-108">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="acc9c-109">El tipo subyacente debe ser uno de los tipos enteros ( `Byte` , `Short` o) `Long` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="acc9c-109">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="acc9c-110">`Integer` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="acc9c-110">`Integer` is the default.</span></span> <span data-ttu-id="acc9c-111">Las enumeraciones siempre tienen un tipo seguro y no son intercambiables con tipos de números enteros.</span><span class="sxs-lookup"><span data-stu-id="acc9c-111">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="acc9c-112">Las enumeraciones no pueden tener valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="acc9c-112">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="acc9c-113">Si se asigna un valor de punto flotante a una enumeración con `Option Strict On` , se producirá un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="acc9c-113">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="acc9c-114">Si `Option Strict` es `Off` , el valor se convierte automáticamente al `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="acc9c-114">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="acc9c-115">Para obtener información sobre los nombres y el uso de la `Imports` instrucción para que la calificación de nombres sea innecesaria, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="acc9c-115">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="acc9c-116">Para declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="acc9c-116">To declare an enumeration</span></span>  
  
1. <span data-ttu-id="acc9c-117">Escriba una declaración que incluya un nivel de acceso de código, la `Enum` palabra clave y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara un diferente `Enum` .</span><span class="sxs-lookup"><span data-stu-id="acc9c-117">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. <span data-ttu-id="acc9c-118">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="acc9c-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="acc9c-119">De forma predeterminada, la primera constante de una enumeración se inicializa en `0` y las constantes subsiguientes se inicializan en un valor de uno más que la constante anterior.</span><span class="sxs-lookup"><span data-stu-id="acc9c-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="acc9c-120">Por ejemplo, la enumeración siguiente, `Days` , contiene una constante denominada `Sunday` con el valor `0` , una constante denominada `Monday` con el valor `1` , una constante denominada `Tuesday` con el valor de `2` , etc.</span><span class="sxs-lookup"><span data-stu-id="acc9c-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. <span data-ttu-id="acc9c-121">Puede asignar valores explícitamente a constantes en una enumeración mediante una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="acc9c-121">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="acc9c-122">Puede asignar cualquier valor entero, incluidos los números negativos.</span><span class="sxs-lookup"><span data-stu-id="acc9c-122">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="acc9c-123">Por ejemplo, puede que desee usar constantes con valores inferiores a cero para representar condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="acc9c-123">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="acc9c-124">En la enumeración siguiente, a la constante `Invalid` se le asigna explícitamente el valor `–1` y se asigna el valor a la constante `Sunday` `0` .</span><span class="sxs-lookup"><span data-stu-id="acc9c-124">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="acc9c-125">Dado que es la primera constante de la enumeración, `Saturday` también se inicializa en el valor `0` .</span><span class="sxs-lookup"><span data-stu-id="acc9c-125">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="acc9c-126">El valor de `Monday` es `1` (uno más que el valor de `Sunday` ); el valor de `Tuesday` es `2` , etc.</span><span class="sxs-lookup"><span data-stu-id="acc9c-126">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="acc9c-127">Para declarar una enumeración como un tipo explícito</span><span class="sxs-lookup"><span data-stu-id="acc9c-127">To declare an enumeration as an explicit type</span></span>  
  
- <span data-ttu-id="acc9c-128">Especifique el tipo de la enumeración mediante la `As` cláusula, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="acc9c-128">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="acc9c-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acc9c-129">See also</span></span>

- [<span data-ttu-id="acc9c-130">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="acc9c-130">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="acc9c-131">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="acc9c-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="acc9c-132">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acc9c-132">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="acc9c-133">Procedimiento para determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="acc9c-133">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="acc9c-134">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="acc9c-134">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="acc9c-135">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="acc9c-135">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="acc9c-136">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="acc9c-136">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="acc9c-137">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="acc9c-137">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
