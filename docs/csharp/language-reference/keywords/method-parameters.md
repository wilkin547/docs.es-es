---
title: Parámetros de métodos (Referencia de C#)
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
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 35d96066deb866e02f6bf624121376fe3ae94373
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="c37bf-102">Parámetros de métodos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c37bf-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="c37bf-103">Los parámetros declarados para un método sin [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) se pasan al método llamado por valor.</span><span class="sxs-lookup"><span data-stu-id="c37bf-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="c37bf-104">Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="c37bf-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="c37bf-105">Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c37bf-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="c37bf-106">Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:</span><span class="sxs-lookup"><span data-stu-id="c37bf-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="c37bf-107">[params](../../../csharp/language-reference/keywords/params.md) especifica que este parámetro puede tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="c37bf-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="c37bf-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="c37bf-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="c37bf-109">[ref](../../../csharp/language-reference/keywords/ref.md) especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.</span><span class="sxs-lookup"><span data-stu-id="c37bf-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="c37bf-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="c37bf-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c37bf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c37bf-111">See Also</span></span>  
 [<span data-ttu-id="c37bf-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c37bf-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c37bf-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c37bf-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c37bf-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="c37bf-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
