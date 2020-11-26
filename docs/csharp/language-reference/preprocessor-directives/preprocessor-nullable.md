---
description: '#nullable: referencia de C#'
title: '#nullable: referencia de C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099452"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="26089-103">#nullable (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="26089-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="26089-104">La directiva de preprocesador `#nullable` establece el *contexto de anotación que admite un valor NULL* y el *contexto de advertencia que admite un valor NULL*.</span><span class="sxs-lookup"><span data-stu-id="26089-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="26089-105">Esta directiva controla si las anotaciones que admiten un valor NULL surten algún efecto y si se proporcionan advertencias de nulabilidad.</span><span class="sxs-lookup"><span data-stu-id="26089-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="26089-106">Cada contexto está *deshabilitado* o *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="26089-107">Ambos contextos se pueden especificar en el nivel de proyecto (fuera del código fuente de C#).</span><span class="sxs-lookup"><span data-stu-id="26089-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="26089-108">La directiva `#nullable` controla los contextos de anotación y advertencia y tiene prioridad sobre la configuración de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="26089-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="26089-109">Una directiva establece los contextos que controla hasta que otra directiva la invalida o hasta el final del archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="26089-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="26089-110">El efecto de las directivas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="26089-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="26089-111">`#nullable disable`: establece los contextos de advertencia y anotación que admiten un valor NULL en *deshabilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="26089-112">`#nullable enable`: establece los contextos de advertencia y anotación que admiten un valor NULL en *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="26089-113">`#nullable restore`: restaura los contextos de advertencia y anotación que admiten un valor NULL a la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="26089-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="26089-114">`#nullable disable annotations`: establece el contexto de anotación que admite un valor NULL en *deshabilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="26089-115">`#nullable enable annotations`: establece el contexto de anotación que admite un valor NULL en *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="26089-116">`#nullable restore annotations`: restaura el contexto de anotación que admite un valor NULL a la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="26089-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="26089-117">`#nullable disable warnings`: establece el contexto de advertencia que admite un valor NULL en *deshabilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="26089-118">`#nullable enable warnings`: establece el contexto de advertencia que admite un valor NULL en *habilitado*.</span><span class="sxs-lookup"><span data-stu-id="26089-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="26089-119">`#nullable restore warnings`: restaura el contexto de advertencia que admite un valor NULL a la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="26089-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="26089-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="26089-120">See also</span></span>

- [<span data-ttu-id="26089-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="26089-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="26089-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="26089-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="26089-123">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="26089-123">C# Preprocessor Directives</span></span>](./index.md)
