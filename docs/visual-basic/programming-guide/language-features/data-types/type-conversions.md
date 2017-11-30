---
title: Conversiones de tipos en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b46d813b4fcadd975d87b235e9f3350a365949fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="0fc1e-102">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fc1e-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="0fc1e-103">El proceso de cambiar un valor de un tipo de datos a otro tipo se denomina *conversión*.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="0fc1e-104">Las conversiones son *ampliación* o *de restricción*, en función de las capacidades de datos de los tipos implicados.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="0fc1e-105">También son *implícita* o *explícita*, en función de la sintaxis en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fc1e-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0fc1e-106">In This Section</span></span>  
 [<span data-ttu-id="0fc1e-107">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="0fc1e-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="0fc1e-108">Explica las conversiones clasificadas por si el tipo de destino puede contener los datos.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="0fc1e-109">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="0fc1e-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="0fc1e-110">Trata las conversiones clasificadas por si [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="0fc1e-111">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="0fc1e-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="0fc1e-112">Ilustra las conversiones entre cadenas y numérico, `Boolean`, o valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="0fc1e-113">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fc1e-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="0fc1e-114">Muestra cómo convertir un `Object` variable en cualquier otro tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="0fc1e-115">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="0fc1e-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="0fc1e-116">Le guiará por el proceso de conversión entre matrices de distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0fc1e-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0fc1e-117">Related Sections</span></span>  
 [<span data-ttu-id="0fc1e-118">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0fc1e-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="0fc1e-119">Presenta el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipos de datos y describe cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-119">Introduces the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="0fc1e-120">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0fc1e-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="0fc1e-121">Enumera los tipos de datos básicos proporcionados por [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fc1e-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="0fc1e-122">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0fc1e-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="0fc1e-123">Describe algunos problemas comunes que pueden surgir al trabajar con tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="0fc1e-123">Discusses some common problems that can arise when working with data types.</span></span>
