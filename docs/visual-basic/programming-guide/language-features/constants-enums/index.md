---
title: Constantes y enumeraciones
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants [Visual Basic]
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants [Visual Basic], enumerations
- naming conventions [Visual Basic], constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
ms.openlocfilehash: aad4f8b24a43ecc51c372916b438daee72adc405
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058695"
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="fbd4e-102">Constantes y enumeraciones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbd4e-102">Constants and Enumerations in Visual Basic</span></span>

<span data-ttu-id="fbd4e-103">Las constantes son una forma de usar nombres significativos en lugar de un valor que no cambia.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="fbd4e-104">Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="fbd4e-105">Puede usar constantes para proporcionar nombres descriptivos, en lugar de números, de forma que el código sea más legible.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="fbd4e-106">Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="fbd4e-107">Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbd4e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fbd4e-108">In This Section</span></span>  
  
|<span data-ttu-id="fbd4e-109">Término</span><span class="sxs-lookup"><span data-stu-id="fbd4e-109">Term</span></span>|<span data-ttu-id="fbd4e-110">Definición</span><span class="sxs-lookup"><span data-stu-id="fbd4e-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="fbd4e-111">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="fbd4e-111">Constants Overview</span></span>](constants-overview.md)|<span data-ttu-id="fbd4e-112">En los temas de esta sección se describen las constantes y sus usos.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="fbd4e-113">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="fbd4e-113">Enumerations Overview</span></span>](enumerations-overview.md)|<span data-ttu-id="fbd4e-114">En los temas de esta sección se describen las enumeraciones y sus usos.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="fbd4e-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="fbd4e-115">Related Sections</span></span>  
  
|<span data-ttu-id="fbd4e-116">Término</span><span class="sxs-lookup"><span data-stu-id="fbd4e-116">Term</span></span>|<span data-ttu-id="fbd4e-117">Definición</span><span class="sxs-lookup"><span data-stu-id="fbd4e-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="fbd4e-118">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="fbd4e-118">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)|<span data-ttu-id="fbd4e-119">Se describe la instrucción `Const`, que se usa para declarar constantes.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="fbd4e-120">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="fbd4e-120">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)|<span data-ttu-id="fbd4e-121">Se describe la instrucción `Enum`, que se usa para crear enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="fbd4e-122">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fbd4e-122">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="fbd4e-123">Se describe la instrucción `Option Explicit`, que se usa en el nivel de módulo para exigir la declaración explícita de todas las variables de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="fbd4e-124">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fbd4e-124">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)|<span data-ttu-id="fbd4e-125">Se describe la instrucción `Option Infer`, que permite el uso de la inferencia de tipo de variable local en la declaración de variables.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="fbd4e-126">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fbd4e-126">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)|<span data-ttu-id="fbd4e-127">Se describe la instrucción `Option Strict`, que restringe las conversiones de tipos de datos implícitos solo a conversiones de ampliación, no permite el enlace en tiempo de ejecución y no permite tipos implícitos que dan como resultado un tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="fbd4e-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
