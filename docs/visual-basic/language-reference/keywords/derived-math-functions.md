---
title: Funciones matemáticas derivadas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836589"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="6044b-102">Funciones matemáticas derivadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6044b-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="6044b-103">La siguiente tabla muestra las funciones matemáticas no intrínsecos que se pueden derivar de las funciones matemáticas intrínsecas de los <xref:System.Math?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="6044b-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="6044b-104">Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` al archivo o proyecto.</span><span class="sxs-lookup"><span data-stu-id="6044b-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="6044b-105">Función</span><span class="sxs-lookup"><span data-stu-id="6044b-105">Function</span></span>|<span data-ttu-id="6044b-106">Equivalentes derivadas</span><span class="sxs-lookup"><span data-stu-id="6044b-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="6044b-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-107">Secant (Sec(x))</span></span>|<span data-ttu-id="6044b-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="6044b-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="6044b-109">Cosecante (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="6044b-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="6044b-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="6044b-111">Cotangente (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="6044b-112">1 / tan (x)</span><span class="sxs-lookup"><span data-stu-id="6044b-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="6044b-113">Seno inverso (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="6044b-114">ATAN (x / Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="6044b-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="6044b-115">Coseno inverso (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="6044b-116">ATAN (-x / Sqrt (-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="6044b-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="6044b-117">Secante inversa (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="6044b-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="6044b-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="6044b-119">Cosecante inversa (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="6044b-120">ATAN(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="6044b-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="6044b-121">Cotangente inversa (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="6044b-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="6044b-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="6044b-123">Seno hiperbólico (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="6044b-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="6044b-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="6044b-125">Coseno hiperbólico (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="6044b-126">(EXP (x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="6044b-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="6044b-127">Tangente hiperbólica (TANH</span><span class="sxs-lookup"><span data-stu-id="6044b-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="6044b-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="6044b-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="6044b-129">Secante hiperbólica (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="6044b-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="6044b-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="6044b-131">Cosecante hiperbólica (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="6044b-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="6044b-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="6044b-133">Cotangente hiperbólica (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="6044b-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="6044b-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="6044b-135">Seno hiperbólico inverso (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="6044b-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="6044b-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="6044b-137">Coseno hiperbólico inverso (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="6044b-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="6044b-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="6044b-139">Tangente hiperbólica inversa (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="6044b-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="6044b-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="6044b-141">Secante hiperbólica inversa (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="6044b-142">Registro ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="6044b-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="6044b-143">Cosecante hiperbólica inversa (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="6044b-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="6044b-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="6044b-145">Cotangente hiperbólica inversa (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="6044b-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="6044b-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="6044b-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6044b-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="6044b-147">See also</span></span>

- [<span data-ttu-id="6044b-148">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="6044b-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
