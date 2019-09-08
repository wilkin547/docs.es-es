---
title: Semántica de null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: d0b18c0a699840d11f5e4add05147672f9bb69e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792984"
---
# <a name="null-semantics"></a><span data-ttu-id="6bd64-102">Semántica de null</span><span class="sxs-lookup"><span data-stu-id="6bd64-102">Null Semantics</span></span>
<span data-ttu-id="6bd64-103">En la tabla siguiente se proporcionan vínculos a varias partes [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de la `null` documentación`Nothing` donde se tratan los problemas de (en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6bd64-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="6bd64-104">Tema</span><span class="sxs-lookup"><span data-stu-id="6bd64-104">Topic</span></span>|<span data-ttu-id="6bd64-105">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6bd64-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6bd64-106">Desajustes de tipos entre SQL y CLR</span><span class="sxs-lookup"><span data-stu-id="6bd64-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="6bd64-107">La sección relativa a la semántica de valores NULL de este tema incluye la explicación del valor booleano de SQL de tres Estados frente al Common Language Runtime de dos <xref:System.Boolean>Estados (CLR `Nothing` ), el literal `null` (C#Visual Basic) y (), y otros similares problemas.</span><span class="sxs-lookup"><span data-stu-id="6bd64-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="6bd64-108">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="6bd64-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="6bd64-109">La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bd64-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="6bd64-110">System.String (Métodos)</span><span class="sxs-lookup"><span data-stu-id="6bd64-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="6bd64-111">La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.</span><span class="sxs-lookup"><span data-stu-id="6bd64-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="6bd64-112">Cálculo de la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="6bd64-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="6bd64-113">Describe cómo el <xref:System.Linq.Enumerable.Sum%2A> operador se evalúa como `null` (`Nothing` en Visual Basic) en lugar de 0 para una secuencia que solo contiene valores NULL o para una secuencia vacía.</span><span class="sxs-lookup"><span data-stu-id="6bd64-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bd64-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bd64-114">See also</span></span>

- [<span data-ttu-id="6bd64-115">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="6bd64-115">Data Types and Functions</span></span>](data-types-and-functions.md)
