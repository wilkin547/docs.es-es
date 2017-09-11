---
title: espacio de nombres (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="578ec-102">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="578ec-102">namespace (C# Reference)</span></span>
<span data-ttu-id="578ec-103">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="578ec-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="578ec-104">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="578ec-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="578ec-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="578ec-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="578ec-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="578ec-106">Remarks</span></span>  
 <span data-ttu-id="578ec-107">En un espacio de nombres, se pueden declarar uno o varios de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="578ec-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="578ec-108">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="578ec-108">another namespace</span></span>  
  
-   [<span data-ttu-id="578ec-109">class</span><span class="sxs-lookup"><span data-stu-id="578ec-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="578ec-110">interface</span><span class="sxs-lookup"><span data-stu-id="578ec-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="578ec-111">struct</span><span class="sxs-lookup"><span data-stu-id="578ec-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="578ec-112">enum</span><span class="sxs-lookup"><span data-stu-id="578ec-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="578ec-113">delegate</span><span class="sxs-lookup"><span data-stu-id="578ec-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="578ec-114">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="578ec-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="578ec-115">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="578ec-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="578ec-116">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="578ec-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="578ec-117">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="578ec-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="578ec-118">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="578ec-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="578ec-119">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="578ec-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="578ec-120">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="578ec-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="578ec-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="578ec-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="578ec-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="578ec-122">Example</span></span>  
 <span data-ttu-id="578ec-123">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="578ec-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="578ec-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="578ec-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="578ec-125">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="578ec-125">For More Information</span></span>  
 <span data-ttu-id="578ec-126">Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="578ec-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="578ec-127">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="578ec-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="578ec-128">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="578ec-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="578ec-129">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="578ec-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="578ec-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="578ec-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="578ec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="578ec-131">See Also</span></span>  
 <span data-ttu-id="578ec-132">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="578ec-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="578ec-133">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="578ec-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="578ec-134">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="578ec-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="578ec-135">[Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="578ec-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="578ec-136">using</span><span class="sxs-lookup"><span data-stu-id="578ec-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

