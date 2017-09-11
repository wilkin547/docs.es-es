---
title: base (Referencia de C#)
description: "Obtenga información sobre la palabra clave base, que se usa para acceder a los miembros de la clase base desde una clase derivada en C#."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: b3a389d92373b6ba5995a7644b0440f9d8fad9ac
ms.contentlocale: es-es
ms.lasthandoff: 08/17/2017

---
# <a name="base-c-reference"></a><span data-ttu-id="f84bc-103">base (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f84bc-103">base (C# Reference)</span></span>

<span data-ttu-id="f84bc-104">La palabra clave `base` se usa para acceder a los miembros de la clase base desde una clase derivada:</span><span class="sxs-lookup"><span data-stu-id="f84bc-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="f84bc-105">Llamar a un método en la clase base que haya sido reemplazado por otro método.</span><span class="sxs-lookup"><span data-stu-id="f84bc-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="f84bc-106">Especificar a qué constructor de clase base se debe llamar cuando se crean instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f84bc-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="f84bc-107">Solo se permite el acceso a una clase base en un constructor, un método de instancia o un descriptor de acceso de propiedad de instancia.</span><span class="sxs-lookup"><span data-stu-id="f84bc-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="f84bc-108">Usar la palabra clave `base` desde dentro de un método estático constituye un error.</span><span class="sxs-lookup"><span data-stu-id="f84bc-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="f84bc-109">La clase base a la que se obtiene acceso es la especificada en la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="f84bc-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="f84bc-110">Por ejemplo, si especifica `class ClassB : ClassA`, se obtiene acceso a los miembros de ClassA desde ClassB, independientemente de la clase base de ClassA.</span><span class="sxs-lookup"><span data-stu-id="f84bc-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="f84bc-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f84bc-111">Example</span></span>
<span data-ttu-id="f84bc-112">En este ejemplo, la clase base, `Person`, y la clase derivada, `Employee`, tienen un método denominado `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="f84bc-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="f84bc-113">Mediante el uso de la palabra clave `base`, es posible llamar al método `Getinfo` en la clase base desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f84bc-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

<span data-ttu-id="f84bc-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f84bc-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span></span>

<span data-ttu-id="f84bc-115">Para ver más ejemplos, consulte [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) y [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="f84bc-115">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="f84bc-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f84bc-116">Example</span></span>
<span data-ttu-id="f84bc-117">En este ejemplo se muestra cómo especificar el constructor de clase base al que se llama al crear instancias de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f84bc-117">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

<span data-ttu-id="f84bc-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f84bc-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f84bc-119">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f84bc-119">C# language specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f84bc-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f84bc-120">See also</span></span>
 <span data-ttu-id="f84bc-121">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f84bc-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f84bc-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f84bc-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f84bc-123">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f84bc-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="f84bc-124">this</span><span class="sxs-lookup"><span data-stu-id="f84bc-124">this</span></span>](../../../csharp/language-reference/keywords/this.md)
