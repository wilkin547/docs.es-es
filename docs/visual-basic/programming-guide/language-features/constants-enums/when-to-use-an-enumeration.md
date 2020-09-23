---
title: Cuándo se debe utilizar una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 7b1b269a5d28d89cd491bac88fbefd4547fdc3c3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095634"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="d049f-102">Cuándo se debe usar una enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d049f-102">When to Use an Enumeration (Visual Basic)</span></span>

<span data-ttu-id="d049f-103">Las enumeraciones ofrecen una manera sencilla de trabajar con conjuntos de constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d049f-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="d049f-104">Una enumeración, o `Enum` , es un nombre simbólico para un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="d049f-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="d049f-105">Las enumeraciones se tratan como tipos de datos y se pueden usar para crear conjuntos de constantes que se usan con variables y propiedades.</span><span class="sxs-lookup"><span data-stu-id="d049f-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="d049f-106">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="d049f-106">When to Use an Enumeration</span></span>  

 <span data-ttu-id="d049f-107">Siempre que un procedimiento acepte un conjunto limitado de variables, considere la posibilidad de usar una enumeración.</span><span class="sxs-lookup"><span data-stu-id="d049f-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="d049f-108">Las enumeraciones hacen que el código sea más claro y legible, especialmente cuando se usan nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="d049f-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="d049f-109">Las ventajas de utilizar enumeraciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="d049f-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="d049f-110">Reduce los errores causados por la transposición o la escritura indebida de números.</span><span class="sxs-lookup"><span data-stu-id="d049f-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="d049f-111">Facilita el cambio de valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d049f-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="d049f-112">Facilita la lectura del código, lo que significa que es menos probable que se produzcan errores en él.</span><span class="sxs-lookup"><span data-stu-id="d049f-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="d049f-113">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d049f-113">Ensures forward compatibility.</span></span> <span data-ttu-id="d049f-114">Con las enumeraciones, es menos probable que se produzca un error en el código si en el futuro alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="d049f-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="d049f-115">Enumeración de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="d049f-115">Naming Enumerations</span></span>  

 <span data-ttu-id="d049f-116">Use una Convención de nomenclatura para los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="d049f-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="d049f-117">Cuando Visual Basic encuentra un nombre de miembro de enumeración, se puede producir una excepción si otras bibliotecas de tipos a las que se hace referencia contienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="d049f-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="d049f-118">Use un prefijo único que identifique los valores de la aplicación o componente.</span><span class="sxs-lookup"><span data-stu-id="d049f-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="d049f-119">Al hacer referencia a un miembro de una enumeración, debe calificar el nombre del miembro con el nombre de la enumeración, o bien usar la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d049f-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="d049f-120">Para obtener más información, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="d049f-120">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="d049f-121">Enumeraciones predefinidas</span><span class="sxs-lookup"><span data-stu-id="d049f-121">Predefined Enumerations</span></span>  

 <span data-ttu-id="d049f-122">Visual Basic proporciona varias enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult` , para facilitar el código.</span><span class="sxs-lookup"><span data-stu-id="d049f-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="d049f-123">Para obtener una lista de estos [, vea constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="d049f-123">For a list of these see [Constants and Enumerations](../../../language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d049f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d049f-124">See also</span></span>

- [<span data-ttu-id="d049f-125">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="d049f-125">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="d049f-126">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="d049f-126">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="d049f-127">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="d049f-127">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="d049f-128">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d049f-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="d049f-129">Procedimiento para determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="d049f-129">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="d049f-130">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="d049f-130">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="d049f-131">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="d049f-131">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
