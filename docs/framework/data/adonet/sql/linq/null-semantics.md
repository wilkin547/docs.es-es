---
title: "Semántica de null"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a><span data-ttu-id="bfd63-102">Semántica de null</span><span class="sxs-lookup"><span data-stu-id="bfd63-102">Null Semantics</span></span>
<span data-ttu-id="bfd63-103">La tabla siguiente proporciona vínculos a varias partes de la documentación de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] donde se analizan los problemas de valores `null` (`Nothing` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="bfd63-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="bfd63-104">Tema</span><span class="sxs-lookup"><span data-stu-id="bfd63-104">Topic</span></span>|<span data-ttu-id="bfd63-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfd63-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bfd63-106">Desajustes de tipos entre SQL y CLR</span><span class="sxs-lookup"><span data-stu-id="bfd63-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="bfd63-107">La sección relativa a la semántica de valores Null de este tema analiza el valor booleano SQL de tres estados frente al objeto <xref:System.Boolean>de dos estados de Common Language Runtime (CLR), los valores literales `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) y `null` (C#), y otros problemas similares.</span><span class="sxs-lookup"><span data-stu-id="bfd63-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="bfd63-108">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="bfd63-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="bfd63-109">La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfd63-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="bfd63-110">System.String (Métodos)</span><span class="sxs-lookup"><span data-stu-id="bfd63-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="bfd63-111">La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.</span><span class="sxs-lookup"><span data-stu-id="bfd63-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="bfd63-112">Cálculo de la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="bfd63-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="bfd63-113">Describe cómo el operador <xref:System.Linq.Enumerable.Sum%2A> se evalúa como `null` (`Nothing` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) en lugar de 0 para una secuencia que solo contiene valores nulos o para una secuencia vacía.</span><span class="sxs-lookup"><span data-stu-id="bfd63-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfd63-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfd63-114">See Also</span></span>  
 [<span data-ttu-id="bfd63-115">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="bfd63-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
