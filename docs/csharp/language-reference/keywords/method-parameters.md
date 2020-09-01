---
description: 'Parámetros de métodos: Referencia de C#'
title: 'Parámetros de métodos: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 7090bf1c3df65cf1e65942404f883b49612e7521
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134411"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="d0063-103">Parámetros de métodos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d0063-103">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="d0063-104">Los parámetros declarados para un método sin [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md) se pasan al método llamado por valor.</span><span class="sxs-lookup"><span data-stu-id="d0063-104">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="d0063-105">Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0063-105">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="d0063-106">Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d0063-106">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="d0063-107">Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:</span><span class="sxs-lookup"><span data-stu-id="d0063-107">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="d0063-108">[params](./params.md) especifica que este parámetro puede tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="d0063-108">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="d0063-109">[in](./in-parameter-modifier.md) especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="d0063-109">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="d0063-110">[ref](./ref.md) especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.</span><span class="sxs-lookup"><span data-stu-id="d0063-110">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="d0063-111">[out](./out-parameter-modifier.md) especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.</span><span class="sxs-lookup"><span data-stu-id="d0063-111">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0063-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0063-112">See also</span></span>

- [<span data-ttu-id="d0063-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d0063-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d0063-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d0063-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d0063-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="d0063-115">C# Keywords</span></span>](./index.md)
