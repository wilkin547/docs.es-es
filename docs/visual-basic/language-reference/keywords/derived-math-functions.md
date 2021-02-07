---
description: 'Más información sobre: funciones matemáticas derivadas (Visual Basic)'
title: Funciones matemáticas derivadas
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
ms.openlocfilehash: daaed1312f08cecc0c68af0e36d574424fc526a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730777"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="13043-103">Funciones matemáticas derivadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13043-103">Derived Math Functions (Visual Basic)</span></span>

<span data-ttu-id="13043-104">En la tabla siguiente se muestran las funciones matemáticas no intrínsecas que se pueden derivar de las funciones matemáticas intrínsecas del <xref:System.Math?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="13043-104">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="13043-105">Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` al archivo o proyecto.</span><span class="sxs-lookup"><span data-stu-id="13043-105">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="13043-106">Función</span><span class="sxs-lookup"><span data-stu-id="13043-106">Function</span></span>|<span data-ttu-id="13043-107">Equivalentes derivados</span><span class="sxs-lookup"><span data-stu-id="13043-107">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="13043-108">Secante (s (x))</span><span class="sxs-lookup"><span data-stu-id="13043-108">Secant (Sec(x))</span></span>|<span data-ttu-id="13043-109">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="13043-109">1 / Cos(x)</span></span>|  
|<span data-ttu-id="13043-110">Cosecante (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="13043-110">Cosecant (Csc(x))</span></span>|<span data-ttu-id="13043-111">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="13043-111">1 / Sin(x)</span></span>|  
|<span data-ttu-id="13043-112">Cotangente (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="13043-112">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="13043-113">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="13043-113">1 / Tan(x)</span></span>|  
|<span data-ttu-id="13043-114">Seno inverso (ASIN (x))</span><span class="sxs-lookup"><span data-stu-id="13043-114">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="13043-115">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="13043-115">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="13043-116">Coseno inverso (ACOS (x))</span><span class="sxs-lookup"><span data-stu-id="13043-116">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="13043-117">Atan (-x/sqrt (-x \* x + 1)) + 2 \* atan (1)</span><span class="sxs-lookup"><span data-stu-id="13043-117">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="13043-118">Secante inversa (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="13043-118">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="13043-119">2 \* atan (1) – atan (signo (x)/raiz (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13043-119">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13043-120">Cosecación inversa (ACSC (x))</span><span class="sxs-lookup"><span data-stu-id="13043-120">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="13043-121">Atan (signo (x)/raiz (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13043-121">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13043-122">Cotangente inversa (ACOT (x))</span><span class="sxs-lookup"><span data-stu-id="13043-122">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="13043-123">2 \* atan (1)-atan (x)</span><span class="sxs-lookup"><span data-stu-id="13043-123">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="13043-124">Seno hiperbólico (SENOH (x))</span><span class="sxs-lookup"><span data-stu-id="13043-124">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="13043-125">(Exp (x) – exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="13043-125">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="13043-126">Coseno hiperbólico (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="13043-126">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="13043-127">(Exp (x) + exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="13043-127">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="13043-128">Tangente hiperbólica (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="13043-128">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="13043-129">(Exp (x) – exp (-x))/(exp (x) + exp (-x))</span><span class="sxs-lookup"><span data-stu-id="13043-129">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="13043-130">Secante hiperbólica (SECH (x))</span><span class="sxs-lookup"><span data-stu-id="13043-130">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="13043-131">2/(exp (x) + exp (-x))</span><span class="sxs-lookup"><span data-stu-id="13043-131">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="13043-132">Cosecante hiperbólica (Csch (x))</span><span class="sxs-lookup"><span data-stu-id="13043-132">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="13043-133">2/(exp (x) – exp (-x))</span><span class="sxs-lookup"><span data-stu-id="13043-133">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="13043-134">Cotangente hiperbólica (coth (x))</span><span class="sxs-lookup"><span data-stu-id="13043-134">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="13043-135">(Exp (x) + exp (-x))/(exp (x) – exp (-x))</span><span class="sxs-lookup"><span data-stu-id="13043-135">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="13043-136">Seno hiperbólico inverso (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="13043-136">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="13043-137">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="13043-137">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="13043-138">Coseno hiperbólico inverso (Acosh (x))</span><span class="sxs-lookup"><span data-stu-id="13043-138">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="13043-139">Log (x + sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="13043-139">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="13043-140">Tangente hiperbólica inversa (Atanh (x))</span><span class="sxs-lookup"><span data-stu-id="13043-140">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="13043-141">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="13043-141">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="13043-142">Secante hiperbólica inversa (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="13043-142">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="13043-143">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="13043-143">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="13043-144">Cosecante hiperbólica inversa (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="13043-144">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="13043-145">Log ((signo (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="13043-145">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="13043-146">Cotangente hiperbólica inversa (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="13043-146">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="13043-147">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="13043-147">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13043-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="13043-148">See also</span></span>

- [<span data-ttu-id="13043-149">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="13043-149">Math Functions</span></span>](../functions/math-functions.md)
