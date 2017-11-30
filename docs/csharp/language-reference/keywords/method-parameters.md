---
title: "Parámetros de métodos (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 924e261cc876d2428e28ed0f490beb46b95f96e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="8bd10-102">Parámetros de métodos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8bd10-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="8bd10-103">Si un parámetro se declara para un método sin [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md), se le puede asociar un valor.</span><span class="sxs-lookup"><span data-stu-id="8bd10-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="8bd10-104">Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="8bd10-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="8bd10-105">Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8bd10-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="8bd10-106">Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd10-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="8bd10-107">params</span><span class="sxs-lookup"><span data-stu-id="8bd10-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="8bd10-108">ref</span><span class="sxs-lookup"><span data-stu-id="8bd10-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="8bd10-109">out</span><span class="sxs-lookup"><span data-stu-id="8bd10-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="8bd10-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bd10-110">See Also</span></span>  
 [<span data-ttu-id="8bd10-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8bd10-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8bd10-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8bd10-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8bd10-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8bd10-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
