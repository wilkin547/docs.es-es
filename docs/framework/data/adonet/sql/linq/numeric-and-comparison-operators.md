---
title: "Operadores numéricos y de comparación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f77cb612468b401f6aa526e46cc7481d0b47d385
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="008ec-102">Operadores numéricos y de comparación</span><span class="sxs-lookup"><span data-stu-id="008ec-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="008ec-103">Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="008ec-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="008ec-104">SQL no admite al operador de módulo en números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="008ec-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="008ec-105">SQL no admite la aritmética no comprobada.</span><span class="sxs-lookup"><span data-stu-id="008ec-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="008ec-106">Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.</span><span class="sxs-lookup"><span data-stu-id="008ec-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="008ec-107">Operadores compatibles</span><span class="sxs-lookup"><span data-stu-id="008ec-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="008ec-108"> admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="008ec-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="008ec-109">Operadores aritméticos básicos:</span><span class="sxs-lookup"><span data-stu-id="008ec-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="008ec-110">`-` (resta)</span><span class="sxs-lookup"><span data-stu-id="008ec-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="008ec-111">División de enteros en Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="008ec-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="008ec-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="008ec-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="008ec-113">`-` (negación unaria)</span><span class="sxs-lookup"><span data-stu-id="008ec-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="008ec-114">Operadores de comparación básicos:</span><span class="sxs-lookup"><span data-stu-id="008ec-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="008ec-115">`=` en Visual Basic y `==` en C#</span><span class="sxs-lookup"><span data-stu-id="008ec-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="008ec-116">`<>` en Visual Basic y `!=` en C#</span><span class="sxs-lookup"><span data-stu-id="008ec-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="008ec-117">`Is/IsNot` en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="008ec-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="008ec-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="008ec-118">See Also</span></span>  
 [<span data-ttu-id="008ec-119">Funciones y tipos de datos</span><span class="sxs-lookup"><span data-stu-id="008ec-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="008ec-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="008ec-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="008ec-121">Operadores</span><span class="sxs-lookup"><span data-stu-id="008ec-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
