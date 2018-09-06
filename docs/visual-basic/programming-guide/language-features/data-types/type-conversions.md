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
ms.openlocfilehash: 026b2a250abfac0782feb0946bc50a94f504f7ed
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037008"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="7a287-102">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a287-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="7a287-103">El proceso de cambiar un valor de un tipo de datos a otro tipo se denomina *conversión*.</span><span class="sxs-lookup"><span data-stu-id="7a287-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="7a287-104">Las conversiones son *ampliación* o *restricción*, según las capacidades de datos de los tipos implicados.</span><span class="sxs-lookup"><span data-stu-id="7a287-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="7a287-105">También son *implícita* o *explícita*, en función de la sintaxis en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="7a287-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a287-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7a287-106">In This Section</span></span>  
 [<span data-ttu-id="7a287-107">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="7a287-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="7a287-108">Explica las conversiones clasificadas por si el tipo de destino puede contener los datos.</span><span class="sxs-lookup"><span data-stu-id="7a287-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="7a287-109">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="7a287-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="7a287-110">Trata las conversiones clasificadas por si Visual Basic las realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a287-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="7a287-111">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="7a287-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="7a287-112">Ilustra las conversiones entre cadenas y numéricos, `Boolean`, o los valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="7a287-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="7a287-113">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a287-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="7a287-114">Se muestra cómo convertir un `Object` variable en cualquier otro tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="7a287-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="7a287-115">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="7a287-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="7a287-116">Los pasos a través del proceso de conversión entre matrices de tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7a287-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a287-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7a287-117">Related Sections</span></span>  
 [<span data-ttu-id="7a287-118">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7a287-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="7a287-119">Presenta a los tipos de datos de Visual Basic y se describe cómo utilizar estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="7a287-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="7a287-120">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7a287-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="7a287-121">Muestra los tipos de datos básicos proporcionados por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7a287-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="7a287-122">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7a287-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="7a287-123">Describe algunos problemas comunes que pueden surgir al trabajar con tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="7a287-123">Discusses some common problems that can arise when working with data types.</span></span>
