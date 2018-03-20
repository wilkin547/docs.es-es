---
title: "Parámetros de métodos (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b20d2d233350cfb9de55cbd07e722082ec311597
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="935ea-102">Parámetros de métodos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="935ea-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="935ea-103">Los parámetros declarados para un método sin [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) se pasan al método llamado por valor.</span><span class="sxs-lookup"><span data-stu-id="935ea-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="935ea-104">Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="935ea-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="935ea-105">Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="935ea-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="935ea-106">Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:</span><span class="sxs-lookup"><span data-stu-id="935ea-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="935ea-107">params</span><span class="sxs-lookup"><span data-stu-id="935ea-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="935ea-108">in</span><span class="sxs-lookup"><span data-stu-id="935ea-108">in</span></span>](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
  
-   [<span data-ttu-id="935ea-109">ref</span><span class="sxs-lookup"><span data-stu-id="935ea-109">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="935ea-110">out</span><span class="sxs-lookup"><span data-stu-id="935ea-110">out</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
  
## <a name="see-also"></a><span data-ttu-id="935ea-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="935ea-111">See Also</span></span>  
 [<span data-ttu-id="935ea-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="935ea-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="935ea-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="935ea-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="935ea-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="935ea-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
