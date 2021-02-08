---
description: 'Más información sobre: BC32124: los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase'
title: Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 0014720d55dc4395178186b5e183d5b0279d7029
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796150"
---
# <a name="bc32124-generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="1faf9-103">BC32124: los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase</span><span class="sxs-lookup"><span data-stu-id="1faf9-103">BC32124: Generic parameters used as optional parameter types must be class constrained</span></span>

<span data-ttu-id="1faf9-104">Se declara un procedimiento con un parámetro opcional que usa un parámetro de tipo que no está restringido para ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="1faf9-104">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>

 <span data-ttu-id="1faf9-105">Siempre debe proporcionar un valor predeterminado para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="1faf9-105">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="1faf9-106">Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing` , que es un valor válido para cualquier tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="1faf9-106">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="1faf9-107">Sin embargo, si el parámetro es de un tipo de valor, ese tipo debe ser un tipo de datos elemental predefinido por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1faf9-107">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="1faf9-108">Esto se debe a que un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="1faf9-108">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>

 <span data-ttu-id="1faf9-109">Cuando se usa un parámetro de tipo para un parámetro opcional, se debe garantizar que sea de un tipo de referencia para evitar la posibilidad de que se produzca un tipo de valor sin un valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="1faf9-109">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="1faf9-110">Esto significa que debe restringir el parámetro de tipo con la `Class` palabra clave o con el nombre de una clase específica.</span><span class="sxs-lookup"><span data-stu-id="1faf9-110">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>

 <span data-ttu-id="1faf9-111">**Identificador de error:** BC32124</span><span class="sxs-lookup"><span data-stu-id="1faf9-111">**Error ID:** BC32124</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1faf9-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1faf9-112">To correct this error</span></span>

- <span data-ttu-id="1faf9-113">Restrinja el parámetro de tipo para que acepte solo un tipo de referencia o no lo use para el parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="1faf9-113">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="1faf9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1faf9-114">See also</span></span>

- [<span data-ttu-id="1faf9-115">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1faf9-115">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="1faf9-116">Type List</span><span class="sxs-lookup"><span data-stu-id="1faf9-116">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="1faf9-117">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="1faf9-117">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="1faf9-118">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="1faf9-118">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="1faf9-119">Estructuras</span><span class="sxs-lookup"><span data-stu-id="1faf9-119">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="1faf9-120">Nothing</span><span class="sxs-lookup"><span data-stu-id="1faf9-120">Nothing</span></span>](../nothing.md)
