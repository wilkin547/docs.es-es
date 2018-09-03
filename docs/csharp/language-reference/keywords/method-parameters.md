---
title: Parámetros de métodos (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 446a5239fa1de8559dea50f7e8b8869aed0297c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390005"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="6b5d2-102">Parámetros de métodos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6b5d2-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="6b5d2-103">Los parámetros declarados para un método sin [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) se pasan al método llamado por valor.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="6b5d2-104">Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="6b5d2-105">Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="6b5d2-106">Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:</span><span class="sxs-lookup"><span data-stu-id="6b5d2-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="6b5d2-107">[params](../../../csharp/language-reference/keywords/params.md) especifica que este parámetro puede tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="6b5d2-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="6b5d2-109">[ref](../../../csharp/language-reference/keywords/ref.md) especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="6b5d2-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="6b5d2-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b5d2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b5d2-111">See Also</span></span>

- [<span data-ttu-id="6b5d2-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6b5d2-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6b5d2-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6b5d2-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6b5d2-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6b5d2-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
