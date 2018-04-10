---
title: Constantes y enumeraciones en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5bbba6434d8b0a5c02882d1ac858296fd8eeb346
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="7d53f-102">Constantes y enumeraciones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d53f-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="7d53f-103">Las constantes son una forma de usar nombres significativos en lugar de un valor que no cambia.</span><span class="sxs-lookup"><span data-stu-id="7d53f-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="7d53f-104">Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d53f-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="7d53f-105">Puede usar constantes para proporcionar nombres descriptivos, en lugar de números, de forma que el código sea más legible.</span><span class="sxs-lookup"><span data-stu-id="7d53f-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="7d53f-106">Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="7d53f-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="7d53f-107">Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.</span><span class="sxs-lookup"><span data-stu-id="7d53f-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d53f-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7d53f-108">In This Section</span></span>  
  
|<span data-ttu-id="7d53f-109">Término</span><span class="sxs-lookup"><span data-stu-id="7d53f-109">Term</span></span>|<span data-ttu-id="7d53f-110">Definición</span><span class="sxs-lookup"><span data-stu-id="7d53f-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="7d53f-111">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="7d53f-111">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)|<span data-ttu-id="7d53f-112">En los temas de esta sección se describen las constantes y sus usos.</span><span class="sxs-lookup"><span data-stu-id="7d53f-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="7d53f-113">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="7d53f-113">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)|<span data-ttu-id="7d53f-114">En los temas de esta sección se describen las enumeraciones y sus usos.</span><span class="sxs-lookup"><span data-stu-id="7d53f-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7d53f-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7d53f-115">Related Sections</span></span>  
  
|<span data-ttu-id="7d53f-116">Término</span><span class="sxs-lookup"><span data-stu-id="7d53f-116">Term</span></span>|<span data-ttu-id="7d53f-117">Definición</span><span class="sxs-lookup"><span data-stu-id="7d53f-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="7d53f-118">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d53f-118">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="7d53f-119">Se describe la instrucción `Const`, que se usa para declarar constantes.</span><span class="sxs-lookup"><span data-stu-id="7d53f-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="7d53f-120">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d53f-120">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)|<span data-ttu-id="7d53f-121">Se describe la instrucción `Enum`, que se usa para crear enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="7d53f-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="7d53f-122">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d53f-122">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="7d53f-123">Se describe la instrucción `Option Explicit`, que se usa en el nivel de módulo para exigir la declaración explícita de todas las variables de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="7d53f-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="7d53f-124">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d53f-124">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)|<span data-ttu-id="7d53f-125">Se describe la instrucción `Option Infer`, que permite el uso de la inferencia de tipo de variable local en la declaración de variables.</span><span class="sxs-lookup"><span data-stu-id="7d53f-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="7d53f-126">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d53f-126">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="7d53f-127">Se describe la instrucción `Option Strict`, que restringe las conversiones de tipos de datos implícitos solo a conversiones de ampliación, no permite el enlace en tiempo de ejecución y no permite tipos implícitos que dan como resultado un tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="7d53f-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
