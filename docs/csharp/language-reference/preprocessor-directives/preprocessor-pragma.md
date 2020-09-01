---
description: '#pragma: Referencia de C#'
title: '#pragma: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 97d7a786c83a8be21f7fd38873061dba0f9278ae
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137960"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="30394-103">#pragma (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="30394-103">#pragma (C# Reference)</span></span>
<span data-ttu-id="30394-104">`#pragma` proporciona al compilador instrucciones especiales para la compilación del archivo en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="30394-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="30394-105">Las instrucciones deben ser compatibles con el compilador.</span><span class="sxs-lookup"><span data-stu-id="30394-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="30394-106">En otras palabras, no puede usar `#pragma` para crear instrucciones de preprocesamiento personalizadas.</span><span class="sxs-lookup"><span data-stu-id="30394-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="30394-107">El compilador de Microsoft C# admite las siguientes dos instrucciones `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="30394-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="30394-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="30394-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="30394-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="30394-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="30394-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30394-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="30394-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30394-111">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="30394-112">El nombre de una pragma reconocida.</span><span class="sxs-lookup"><span data-stu-id="30394-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="30394-113">Argumentos específicos de pragma.</span><span class="sxs-lookup"><span data-stu-id="30394-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30394-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="30394-114">See also</span></span>

- [<span data-ttu-id="30394-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="30394-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="30394-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="30394-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="30394-117">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="30394-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="30394-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="30394-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="30394-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="30394-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
