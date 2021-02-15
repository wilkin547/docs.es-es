---
description: 'Más información acerca de: Cuándo usar una enumeración (Visual Basic)'
title: Cuándo se debe utilizar una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: a29d0e3bb8ac99baf5d43827a8b58701eddcfbdd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480744"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="9f5e0-103">Cuándo se debe usar una enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f5e0-103">When to Use an Enumeration (Visual Basic)</span></span>

<span data-ttu-id="9f5e0-104">Las enumeraciones ofrecen una manera sencilla de trabajar con conjuntos de constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-104">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="9f5e0-105">Una enumeración, o `Enum` , es un nombre simbólico para un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-105">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="9f5e0-106">Las enumeraciones se tratan como tipos de datos y se pueden usar para crear conjuntos de constantes que se usan con variables y propiedades.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-106">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="9f5e0-107">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="9f5e0-107">When to Use an Enumeration</span></span>  

 <span data-ttu-id="9f5e0-108">Siempre que un procedimiento acepte un conjunto limitado de variables, considere la posibilidad de usar una enumeración.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-108">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="9f5e0-109">Las enumeraciones hacen que el código sea más claro y legible, especialmente cuando se usan nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-109">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="9f5e0-110">Las ventajas de utilizar enumeraciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="9f5e0-110">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="9f5e0-111">Reduce los errores causados por la transposición o la escritura indebida de números.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-111">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="9f5e0-112">Facilita el cambio de valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-112">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="9f5e0-113">Facilita la lectura del código, lo que significa que es menos probable que se produzcan errores en él.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-113">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="9f5e0-114">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-114">Ensures forward compatibility.</span></span> <span data-ttu-id="9f5e0-115">Con las enumeraciones, es menos probable que se produzca un error en el código si en el futuro alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-115">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="9f5e0-116">Enumeración de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="9f5e0-116">Naming Enumerations</span></span>  

 <span data-ttu-id="9f5e0-117">Use una Convención de nomenclatura para los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-117">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="9f5e0-118">Cuando Visual Basic encuentra un nombre de miembro de enumeración, se puede producir una excepción si otras bibliotecas de tipos a las que se hace referencia contienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-118">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="9f5e0-119">Use un prefijo único que identifique los valores de la aplicación o componente.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-119">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="9f5e0-120">Al hacer referencia a un miembro de una enumeración, debe calificar el nombre del miembro con el nombre de la enumeración, o bien usar la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-120">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="9f5e0-121">Para obtener más información, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="9f5e0-121">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="9f5e0-122">Enumeraciones predefinidas</span><span class="sxs-lookup"><span data-stu-id="9f5e0-122">Predefined Enumerations</span></span>  

 <span data-ttu-id="9f5e0-123">Visual Basic proporciona varias enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult` , para facilitar el código.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-123">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="9f5e0-124">Para obtener una lista de estos [, vea constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="9f5e0-124">For a list of these see [Constants and Enumerations](../../../language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5e0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f5e0-125">See also</span></span>

- [<span data-ttu-id="9f5e0-126">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="9f5e0-126">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="9f5e0-127">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="9f5e0-127">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="9f5e0-128">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="9f5e0-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="9f5e0-129">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f5e0-129">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="9f5e0-130">Procedimiento para determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="9f5e0-130">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="9f5e0-131">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="9f5e0-131">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="9f5e0-132">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="9f5e0-132">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
