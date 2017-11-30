---
title: espacio de nombres (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76cc1adc21f6cfadc93da58250336705e43e333a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-c-reference"></a><span data-ttu-id="a576b-102">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a576b-102">namespace (C# Reference)</span></span>
<span data-ttu-id="a576b-103">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a576b-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="a576b-104">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="a576b-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="a576b-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a576b-105">Remarks</span></span>  
 <span data-ttu-id="a576b-106">En un espacio de nombres, se pueden declarar uno o varios de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="a576b-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="a576b-107">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a576b-107">another namespace</span></span>  
  
-   [<span data-ttu-id="a576b-108">class</span><span class="sxs-lookup"><span data-stu-id="a576b-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="a576b-109">interface</span><span class="sxs-lookup"><span data-stu-id="a576b-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="a576b-110">struct</span><span class="sxs-lookup"><span data-stu-id="a576b-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="a576b-111">enum</span><span class="sxs-lookup"><span data-stu-id="a576b-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="a576b-112">delegate</span><span class="sxs-lookup"><span data-stu-id="a576b-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="a576b-113">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a576b-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="a576b-114">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="a576b-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="a576b-115">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="a576b-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="a576b-116">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="a576b-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="a576b-117">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a576b-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="a576b-118">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="a576b-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="a576b-119">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="a576b-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="a576b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a576b-120">Example</span></span>  
 <span data-ttu-id="a576b-121">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="a576b-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="a576b-122">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="a576b-122">For More Information</span></span>  
 <span data-ttu-id="a576b-123">Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a576b-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a576b-124">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a576b-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="a576b-125">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a576b-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="a576b-126">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="a576b-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="a576b-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a576b-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a576b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a576b-128">See Also</span></span>  
 [<span data-ttu-id="a576b-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a576b-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a576b-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a576b-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a576b-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a576b-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a576b-132">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a576b-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="a576b-133">using</span><span class="sxs-lookup"><span data-stu-id="a576b-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
