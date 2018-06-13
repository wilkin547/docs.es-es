---
title: Conversiones de tipos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 7f1a571cda4f68222c5c03c3a8fe31c29eafd8c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647219"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="82315-102">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82315-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="82315-103">El proceso de cambiar un valor de un tipo de datos a otro tipo se denomina *conversión*.</span><span class="sxs-lookup"><span data-stu-id="82315-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="82315-104">Las conversiones son *ampliación* o *de restricción*, en función de las capacidades de datos de los tipos implicados.</span><span class="sxs-lookup"><span data-stu-id="82315-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="82315-105">También son *implícita* o *explícita*, en función de la sintaxis en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="82315-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82315-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="82315-106">In This Section</span></span>  
 [<span data-ttu-id="82315-107">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="82315-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="82315-108">Explica las conversiones clasificadas por si el tipo de destino puede contener los datos.</span><span class="sxs-lookup"><span data-stu-id="82315-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="82315-109">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="82315-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="82315-110">Trata las conversiones clasificadas por si Visual Basic las realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="82315-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="82315-111">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="82315-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="82315-112">Ilustra las conversiones entre cadenas y numérico, `Boolean`, o valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="82315-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="82315-113">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82315-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="82315-114">Muestra cómo convertir un `Object` variable en cualquier otro tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="82315-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="82315-115">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="82315-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="82315-116">Le guiará por el proceso de conversión entre matrices de distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="82315-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82315-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="82315-117">Related Sections</span></span>  
 [<span data-ttu-id="82315-118">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="82315-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="82315-119">Presenta a los tipos de datos de Visual Basic y describe cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="82315-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="82315-120">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="82315-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="82315-121">Muestra los tipos de datos básicos proporcionados por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="82315-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="82315-122">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="82315-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="82315-123">Describe algunos problemas comunes que pueden surgir al trabajar con tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="82315-123">Discusses some common problems that can arise when working with data types.</span></span>
