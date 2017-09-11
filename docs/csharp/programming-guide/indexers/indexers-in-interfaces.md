---
title: "Indizadores en interfaces (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
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
ms.openlocfilehash: 2715602dadea40324f613bb07b5dd332ed18c25c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="0e172-102">Indizadores en interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0e172-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="0e172-103">Los indexadores se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="0e172-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="0e172-104">Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../../csharp/language-reference/keywords/class.md) de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e172-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="0e172-105">Los descriptores de acceso de interfaz no usan modificadores.</span><span class="sxs-lookup"><span data-stu-id="0e172-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="0e172-106">Un descriptor de acceso de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="0e172-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="0e172-107">Por tanto, el propósito del descriptor de acceso es indicar si el indexador es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="0e172-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="0e172-108">A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:</span><span class="sxs-lookup"><span data-stu-id="0e172-108">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="0e172-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0e172-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="0e172-110">La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e172-110">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e172-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e172-111">Example</span></span>  
 <span data-ttu-id="0e172-112">En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e172-112">The following example shows how to implement interface indexers.</span></span>  
  
 <span data-ttu-id="0e172-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0e172-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="0e172-114">En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e172-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="0e172-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e172-115">For example:</span></span>  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 <span data-ttu-id="0e172-116">En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador.</span><span class="sxs-lookup"><span data-stu-id="0e172-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="0e172-117">Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria.</span><span class="sxs-lookup"><span data-stu-id="0e172-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="0e172-118">Es decir, la siguiente declaración de indexador:</span><span class="sxs-lookup"><span data-stu-id="0e172-118">That is, the following indexer declaration:</span></span>  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 <span data-ttu-id="0e172-119">implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="0e172-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 <span data-ttu-id="0e172-120">implementa el indexador en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="0e172-120">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e172-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e172-121">See Also</span></span>  
 <span data-ttu-id="0e172-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e172-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0e172-123">[Indexers](../../../csharp/programming-guide/indexers/index.md)  (Indexadores)</span><span class="sxs-lookup"><span data-stu-id="0e172-123">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="0e172-124">[Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="0e172-124">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="0e172-125">Interfaces</span><span class="sxs-lookup"><span data-stu-id="0e172-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

