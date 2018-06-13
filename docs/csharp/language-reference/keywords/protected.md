---
title: protected (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: a3115fe82b452f52ee75cf222302ece0fc67b330
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269575"
---
# <a name="protected-c-reference"></a><span data-ttu-id="4e429-102">protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4e429-102">protected (C# Reference)</span></span>
<span data-ttu-id="4e429-103">La palabra clave `protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="4e429-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="4e429-104">Esta página trata sobre el modificador de acceso `protected`.</span><span class="sxs-lookup"><span data-stu-id="4e429-104">This page covers `protected` access.</span></span> <span data-ttu-id="4e429-105">La palabra clave `protected` también forma parte de los modificadores de acceso [`protected internal`](./protected-internal.md) y [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="4e429-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="4e429-106">Un miembro protegido es accesible dentro de su clase y por parte de instancias de clase derivadas.</span><span class="sxs-lookup"><span data-stu-id="4e429-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="4e429-107">Para obtener una comparación de `protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4e429-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="4e429-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e429-108">Example</span></span>  
 <span data-ttu-id="4e429-109">Un miembro protegido de una clase base es accesible en una clase derivada únicamente si el acceso se produce a través del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4e429-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="4e429-110">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="4e429-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="4e429-111">La instrucción `a.x = 10` genera un error porque se ha creado en el método estático Main y no en una instancia de clase B.</span><span class="sxs-lookup"><span data-stu-id="4e429-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="4e429-112">Los miembros de estructura no se pueden proteger porque la estructura no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="4e429-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e429-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e429-113">Example</span></span>  
 <span data-ttu-id="4e429-114">En este ejemplo, la clase `DerivedPoint` se deriva de `Point`.</span><span class="sxs-lookup"><span data-stu-id="4e429-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="4e429-115">Por lo tanto, puede acceder a los miembros protegidos de la clase base directamente desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4e429-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="4e429-116">Si cambia los niveles de acceso de `x` y `y` a [private](../../../csharp/language-reference/keywords/private.md), el compilador genera los mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="4e429-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="4e429-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4e429-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e429-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e429-118">See Also</span></span>  
 [<span data-ttu-id="4e429-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4e429-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4e429-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4e429-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4e429-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4e429-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4e429-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="4e429-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="4e429-123">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="4e429-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="4e429-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="4e429-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="4e429-125">public</span><span class="sxs-lookup"><span data-stu-id="4e429-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="4e429-126">private</span><span class="sxs-lookup"><span data-stu-id="4e429-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="4e429-127">internal</span><span class="sxs-lookup"><span data-stu-id="4e429-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="4e429-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="4e429-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>