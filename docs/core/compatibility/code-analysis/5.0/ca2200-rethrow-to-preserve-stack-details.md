---
title: 'Cambio importante: CA2200: Reiniciar para mantener los detalles de la pila'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA2200.
ms.date: 09/03/2020
ms.openlocfilehash: 776a1bcf16c19364017e4652837720080fb7ba72
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257731"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="20557-103">Advertencia CA2200: Reiniciar para mantener los detalles de la pila</span><span class="sxs-lookup"><span data-stu-id="20557-103">Warning CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="20557-104">La regla [CA2200](/visualstudio/code-quality/ca2200) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="20557-104">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="20557-105">Genera una advertencia de compilación para cualquier bloque `catch` que vuelva a iniciar una excepción y la excepción se especifica de forma explícita en la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="20557-105">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

## <a name="change-description"></a><span data-ttu-id="20557-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="20557-106">Change description</span></span>

<span data-ttu-id="20557-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="20557-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="20557-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="20557-108">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="20557-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="20557-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="20557-110">La regla CA2200 marca el código donde se vuelven a iniciar las excepciones y la variable de excepción se especifica en la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="20557-110">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="20557-111">Cuando se inicia una excepción, parte de la información que contiene es el seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="20557-111">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="20557-112">El seguimiento de la pila es una lista de la jerarquía de llamadas de método que comienza con el método que inicia la excepción y termina con el que la captura.</span><span class="sxs-lookup"><span data-stu-id="20557-112">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="20557-113">Si se especifica una excepción en la instrucción `throw` y la excepción se vuelve a iniciar, el seguimiento de la pila se reinicia en el método actual y se pierde la lista de llamadas de método entre el método original que ha iniciado la excepción y el método actual.</span><span class="sxs-lookup"><span data-stu-id="20557-113">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="20557-114">Para mantener la información de seguimiento de la pila original con la excepción, use la instrucción `throw` sin especificar la excepción.</span><span class="sxs-lookup"><span data-stu-id="20557-114">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="20557-115">El fragmento de código siguiente no genera una advertencia para la regla CA2200.</span><span class="sxs-lookup"><span data-stu-id="20557-115">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="20557-116">Pero la línea comentada *desencadenaría* una infracción.</span><span class="sxs-lookup"><span data-stu-id="20557-116">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a><span data-ttu-id="20557-117">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="20557-117">Version introduced</span></span>

<span data-ttu-id="20557-118">5.0</span><span class="sxs-lookup"><span data-stu-id="20557-118">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="20557-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="20557-119">Recommended action</span></span>

- <span data-ttu-id="20557-120">Vuelva a iniciar las excepciones sin especificar la excepción de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="20557-120">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="20557-121">Para obtener más información, vea [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="20557-121">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="20557-122">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="20557-122">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="20557-123">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="20557-123">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="20557-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="20557-124">Affected APIs</span></span>

<span data-ttu-id="20557-125">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="20557-125">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
