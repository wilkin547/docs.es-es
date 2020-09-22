---
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
ms.openlocfilehash: f84b1ef18ef2a924bb2e47da85ecbb51f982873a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869021"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="cd025-102">Funciones matemáticas derivadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd025-102">Derived Math Functions (Visual Basic)</span></span>

<span data-ttu-id="cd025-103">En la tabla siguiente se muestran las funciones matemáticas no intrínsecas que se pueden derivar de las funciones matemáticas intrínsecas del <xref:System.Math?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="cd025-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="cd025-104">Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` al archivo o proyecto.</span><span class="sxs-lookup"><span data-stu-id="cd025-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="cd025-105">Función</span><span class="sxs-lookup"><span data-stu-id="cd025-105">Function</span></span>|<span data-ttu-id="cd025-106">Equivalentes derivados</span><span class="sxs-lookup"><span data-stu-id="cd025-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="cd025-107">Secante (s (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-107">Secant (Sec(x))</span></span>|<span data-ttu-id="cd025-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="cd025-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="cd025-109">Cosecante (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="cd025-110">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="cd025-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="cd025-111">Cotangente (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="cd025-112">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="cd025-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="cd025-113">Seno inverso (ASIN (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="cd025-114">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="cd025-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="cd025-115">Coseno inverso (ACOS (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="cd025-116">Atan (-x/sqrt (-x \* x + 1)) + 2 \* atan (1)</span><span class="sxs-lookup"><span data-stu-id="cd025-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="cd025-117">Secante inversa (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="cd025-118">2 \* atan (1) – atan (signo (x)/raiz (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cd025-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cd025-119">Cosecación inversa (ACSC (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="cd025-120">Atan (signo (x)/raiz (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cd025-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cd025-121">Cotangente inversa (ACOT (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="cd025-122">2 \* atan (1)-atan (x)</span><span class="sxs-lookup"><span data-stu-id="cd025-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="cd025-123">Seno hiperbólico (SENOH (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="cd025-124">(Exp (x) – exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="cd025-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="cd025-125">Coseno hiperbólico (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="cd025-126">(Exp (x) + exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="cd025-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="cd025-127">Tangente hiperbólica (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="cd025-128">(Exp (x) – exp (-x))/(exp (x) + exp (-x))</span><span class="sxs-lookup"><span data-stu-id="cd025-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="cd025-129">Secante hiperbólica (SECH (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="cd025-130">2/(exp (x) + exp (-x))</span><span class="sxs-lookup"><span data-stu-id="cd025-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="cd025-131">Cosecante hiperbólica (Csch (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="cd025-132">2/(exp (x) – exp (-x))</span><span class="sxs-lookup"><span data-stu-id="cd025-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="cd025-133">Cotangente hiperbólica (coth (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="cd025-134">(Exp (x) + exp (-x))/(exp (x) – exp (-x))</span><span class="sxs-lookup"><span data-stu-id="cd025-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="cd025-135">Seno hiperbólico inverso (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="cd025-136">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="cd025-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="cd025-137">Coseno hiperbólico inverso (Acosh (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="cd025-138">Log (x + sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="cd025-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="cd025-139">Tangente hiperbólica inversa (Atanh (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="cd025-140">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="cd025-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="cd025-141">Secante hiperbólica inversa (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="cd025-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="cd025-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="cd025-143">Cosecante hiperbólica inversa (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="cd025-144">Log ((signo (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="cd025-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="cd025-145">Cotangente hiperbólica inversa (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="cd025-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="cd025-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="cd025-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd025-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd025-147">See also</span></span>

- [<span data-ttu-id="cd025-148">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="cd025-148">Math Functions</span></span>](../functions/math-functions.md)
