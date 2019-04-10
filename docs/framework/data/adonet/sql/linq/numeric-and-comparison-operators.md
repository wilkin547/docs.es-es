---
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 9b31fd2d819afbb1e589ad74f23ec139830c68b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212172"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="95be8-102">Operadores numéricos y de comparación</span><span class="sxs-lookup"><span data-stu-id="95be8-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="95be8-103">Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="95be8-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="95be8-104">SQL no admite al operador de módulo en números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="95be8-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="95be8-105">SQL no admite la aritmética no comprobada.</span><span class="sxs-lookup"><span data-stu-id="95be8-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="95be8-106">Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.</span><span class="sxs-lookup"><span data-stu-id="95be8-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="95be8-107">Operadores compatibles</span><span class="sxs-lookup"><span data-stu-id="95be8-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="95be8-108">admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="95be8-108">supports the following operators.</span></span>  
  
-   <span data-ttu-id="95be8-109">Operadores aritméticos básicos:</span><span class="sxs-lookup"><span data-stu-id="95be8-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   `-` <span data-ttu-id="95be8-110">(resta)</span><span class="sxs-lookup"><span data-stu-id="95be8-110">(subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="95be8-111">División de enteros en Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="95be8-111">Visual Basic integer division (`\`)</span></span>  
  
    -   `%` <span data-ttu-id="95be8-112">(Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="95be8-112">(Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` <span data-ttu-id="95be8-113">(negación unaria)</span><span class="sxs-lookup"><span data-stu-id="95be8-113">(unary negation)</span></span>  
  
-   <span data-ttu-id="95be8-114">Operadores de comparación básicos:</span><span class="sxs-lookup"><span data-stu-id="95be8-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="95be8-115">Visual Basic `=` y C#</span><span class="sxs-lookup"><span data-stu-id="95be8-115">Visual Basic `=` and C#</span></span> `==`  
  
    -   <span data-ttu-id="95be8-116">Visual Basic `<>` y C#</span><span class="sxs-lookup"><span data-stu-id="95be8-116">Visual Basic `<>` and C#</span></span> `!=`  
  
    -   <span data-ttu-id="95be8-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95be8-117">Visual Basic</span></span> `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="95be8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="95be8-118">See also</span></span>

- [<span data-ttu-id="95be8-119">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="95be8-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="95be8-120">operadores de C#</span><span class="sxs-lookup"><span data-stu-id="95be8-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)
- [<span data-ttu-id="95be8-121">Operadores</span><span class="sxs-lookup"><span data-stu-id="95be8-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
