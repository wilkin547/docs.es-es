---
title: '#pragma: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712460"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="9de1b-102">#pragma (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9de1b-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="9de1b-103">`#pragma` proporciona al compilador instrucciones especiales para la compilación del archivo en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="9de1b-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="9de1b-104">Las instrucciones deben ser compatibles con el compilador.</span><span class="sxs-lookup"><span data-stu-id="9de1b-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="9de1b-105">En otras palabras, no puede usar `#pragma` para crear instrucciones de preprocesamiento personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9de1b-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="9de1b-106">El compilador de Microsoft C# admite las siguientes dos instrucciones `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="9de1b-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="9de1b-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="9de1b-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="9de1b-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="9de1b-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="9de1b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9de1b-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de1b-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9de1b-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="9de1b-111">El nombre de una pragma reconocida.</span><span class="sxs-lookup"><span data-stu-id="9de1b-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="9de1b-112">Argumentos específicos de pragma.</span><span class="sxs-lookup"><span data-stu-id="9de1b-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de1b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de1b-113">See also</span></span>

- [<span data-ttu-id="9de1b-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9de1b-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9de1b-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9de1b-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9de1b-116">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="9de1b-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="9de1b-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="9de1b-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="9de1b-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="9de1b-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
