---
title: Semántica de null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147546"
---
# <a name="null-semantics"></a><span data-ttu-id="62354-102">Semántica de null</span><span class="sxs-lookup"><span data-stu-id="62354-102">Null Semantics</span></span>

<span data-ttu-id="62354-103">En la tabla siguiente se proporcionan vínculos a varias partes de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación donde `null` `Nothing` se tratan los problemas de (en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="62354-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="62354-104">Tema</span><span class="sxs-lookup"><span data-stu-id="62354-104">Topic</span></span>|<span data-ttu-id="62354-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="62354-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="62354-106">Desajustes de tipos entre SQL y CLR</span><span class="sxs-lookup"><span data-stu-id="62354-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="62354-107">La sección relativa a la semántica de valores NULL de este tema incluye la explicación del valor booleano de SQL de tres Estados frente al Common Language Runtime de dos Estados (CLR) <xref:System.Boolean> , el literal `Nothing` (Visual Basic) y `null` (C#), y otros problemas similares.</span><span class="sxs-lookup"><span data-stu-id="62354-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="62354-108">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="62354-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="62354-109">La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62354-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="62354-110">System.String (Métodos)</span><span class="sxs-lookup"><span data-stu-id="62354-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="62354-111">La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.</span><span class="sxs-lookup"><span data-stu-id="62354-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="62354-112">Calcular la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="62354-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="62354-113">Describe cómo el <xref:System.Linq.Enumerable.Sum%2A> operador se evalúa como `null` ( `Nothing` en Visual Basic) en lugar de 0 para una secuencia que solo contiene valores NULL o para una secuencia vacía.</span><span class="sxs-lookup"><span data-stu-id="62354-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62354-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="62354-114">See also</span></span>

- [<span data-ttu-id="62354-115">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="62354-115">Data Types and Functions</span></span>](data-types-and-functions.md)
