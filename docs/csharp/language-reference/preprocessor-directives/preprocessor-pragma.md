---
description: '#pragma: Referencia de C#'
title: '#pragma: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168522"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="ab20c-103">#pragma (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ab20c-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="ab20c-104">`#pragma` proporciona al compilador instrucciones especiales para la compilación del archivo en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="ab20c-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="ab20c-105">Las instrucciones deben ser compatibles con el compilador.</span><span class="sxs-lookup"><span data-stu-id="ab20c-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="ab20c-106">En otras palabras, no puede usar `#pragma` para crear instrucciones de preprocesamiento personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ab20c-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="ab20c-107">El compilador de Microsoft C# admite las siguientes dos instrucciones `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="ab20c-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="ab20c-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="ab20c-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="ab20c-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="ab20c-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="ab20c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab20c-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab20c-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab20c-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="ab20c-112">El nombre de una pragma reconocida.</span><span class="sxs-lookup"><span data-stu-id="ab20c-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="ab20c-113">Argumentos específicos de pragma.</span><span class="sxs-lookup"><span data-stu-id="ab20c-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab20c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab20c-114">See also</span></span>

- [<span data-ttu-id="ab20c-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ab20c-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ab20c-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ab20c-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ab20c-117">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="ab20c-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="ab20c-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="ab20c-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="ab20c-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="ab20c-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
