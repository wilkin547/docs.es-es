---
title: "Cómo: Declarar enumeraciones (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="94d98-102">Cómo: Declarar enumeraciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94d98-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="94d98-103">Cree una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="94d98-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="94d98-104">No se puede declarar una enumeración dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="94d98-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="94d98-105">Para especificar el nivel de acceso adecuado, utilice `Private`, `Protected`, `Friend`, o `Public`.</span><span class="sxs-lookup"><span data-stu-id="94d98-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="94d98-106">Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante.</span><span class="sxs-lookup"><span data-stu-id="94d98-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="94d98-107">El nombre debe ser un calificador de Visual Basic .NET válido.</span><span class="sxs-lookup"><span data-stu-id="94d98-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="94d98-108">El tipo subyacente debe ser uno de los tipos de enteros:`Byte`, `Short`, `Long` o `Integer`.</span><span class="sxs-lookup"><span data-stu-id="94d98-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="94d98-109">`Integer` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="94d98-109">`Integer` is the default.</span></span> <span data-ttu-id="94d98-110">Las enumeraciones son siempre establecimiento inflexible de tipos y no son intercambiables con tipos de números enteros.</span><span class="sxs-lookup"><span data-stu-id="94d98-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="94d98-111">Las enumeraciones no pueden tener valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="94d98-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="94d98-112">Si se asigna un valor de punto flotante con una enumeración `Option Strict On`, obtendrá un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="94d98-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="94d98-113">Si `Option Strict` es `Off`, el valor se convierte automáticamente en el `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="94d98-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="94d98-114">Para obtener información sobre nombres y cómo usar el `Imports` instrucción para asegurarse de calificación de nombres no es necesario, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="94d98-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="94d98-115">Para declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="94d98-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="94d98-116">Escriba una declaración que incluya un nivel de acceso del código, el `Enum` palabra clave y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara otra `Enum`.</span><span class="sxs-lookup"><span data-stu-id="94d98-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  <span data-ttu-id="94d98-117">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="94d98-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="94d98-118">De forma predeterminada, la primera constante de una enumeración se inicializa en `0`, y constantes subsiguientes se inicializan con un valor de la constante anterior más uno.</span><span class="sxs-lookup"><span data-stu-id="94d98-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="94d98-119">Por ejemplo, la siguiente enumeración, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor de `2`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="94d98-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  <span data-ttu-id="94d98-120">Puede asignar explícitamente valores a constantes en una enumeración mediante una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="94d98-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="94d98-121">Puede asignar cualquier valor entero, incluidos los números negativos.</span><span class="sxs-lookup"><span data-stu-id="94d98-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="94d98-122">Por ejemplo, puede que desee constantes con valores menores que cero para representar las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="94d98-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="94d98-123">En la siguiente enumeración, la constante `Invalid` no se asigna explícitamente el valor `–1`y la constante `Sunday` se asigna el valor `0`.</span><span class="sxs-lookup"><span data-stu-id="94d98-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="94d98-124">Dado que es la primera constante de la enumeración, `Saturday` también se inicializa con el valor `0`.</span><span class="sxs-lookup"><span data-stu-id="94d98-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="94d98-125">El valor de `Monday` es `1` (uno más que el valor de `Sunday`); el valor de `Tuesday` es `2`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="94d98-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="94d98-126">Para declarar una enumeración como un tipo explícito</span><span class="sxs-lookup"><span data-stu-id="94d98-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="94d98-127">Especificar el tipo de la enumeración mediante el `As` cláusula, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="94d98-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="94d98-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="94d98-128">See Also</span></span>  
 [<span data-ttu-id="94d98-129">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="94d98-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="94d98-130">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="94d98-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="94d98-131">Cómo: recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94d98-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="94d98-132">Determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="94d98-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="94d98-133">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="94d98-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="94d98-134">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="94d98-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="94d98-135">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="94d98-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="94d98-136">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="94d98-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
