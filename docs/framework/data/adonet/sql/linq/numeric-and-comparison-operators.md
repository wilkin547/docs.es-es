---
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: ff54856a66ad5e9c0362c013f8df5f1147055cd0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915704"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="efeb7-102">Operadores numéricos y de comparación</span><span class="sxs-lookup"><span data-stu-id="efeb7-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="efeb7-103">Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="efeb7-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="efeb7-104">SQL no admite al operador de módulo en números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="efeb7-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="efeb7-105">SQL no admite la aritmética no comprobada.</span><span class="sxs-lookup"><span data-stu-id="efeb7-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="efeb7-106">Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.</span><span class="sxs-lookup"><span data-stu-id="efeb7-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="efeb7-107">Operadores compatibles</span><span class="sxs-lookup"><span data-stu-id="efeb7-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="efeb7-108">admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="efeb7-108">supports the following operators.</span></span>

- <span data-ttu-id="efeb7-109">Operadores aritméticos básicos:</span><span class="sxs-lookup"><span data-stu-id="efeb7-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="efeb7-110">`-` (resta)</span><span class="sxs-lookup"><span data-stu-id="efeb7-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="efeb7-111">División de enteros en Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="efeb7-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="efeb7-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="efeb7-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="efeb7-113">`-` (negación unaria)</span><span class="sxs-lookup"><span data-stu-id="efeb7-113">`-` (unary negation)</span></span>

- <span data-ttu-id="efeb7-114">Operadores de comparación básicos:</span><span class="sxs-lookup"><span data-stu-id="efeb7-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="efeb7-115">`=` en Visual Basic y `==` en C#</span><span class="sxs-lookup"><span data-stu-id="efeb7-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="efeb7-116">`<>` en Visual Basic y `!=` en C#</span><span class="sxs-lookup"><span data-stu-id="efeb7-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="efeb7-117">`Is/IsNot` en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efeb7-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="efeb7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="efeb7-118">See also</span></span>

- [<span data-ttu-id="efeb7-119">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="efeb7-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="efeb7-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="efeb7-120">C# Operators</span></span>](../../../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="efeb7-121">Operadores</span><span class="sxs-lookup"><span data-stu-id="efeb7-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
