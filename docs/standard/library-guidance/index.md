---
title: Guía de la biblioteca .NET de código abierto
description: Procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad
ms.date: 10/17/2018
ms.openlocfilehash: c1e1c302eede86fd5555a8e84630e216e96f1ce7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706457"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="c62c4-103">Guía de la biblioteca de código abierto</span><span class="sxs-lookup"><span data-stu-id="c62c4-103">Open-source library guidance</span></span>

<span data-ttu-id="c62c4-104">En esta guía se ofrecen procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="c62c4-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="c62c4-105">Esta documentación se centra en el *qué* y el *porqué* de la compilación de una biblioteca .NET, no en el *cómo*.</span><span class="sxs-lookup"><span data-stu-id="c62c4-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="c62c4-106">Aspectos de las bibliotecas .NET de código abierto de alta calidad:</span><span class="sxs-lookup"><span data-stu-id="c62c4-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="c62c4-107">**Inclusivas**: las bibliotecas. NET de buena calidad deben estar diseñadas para admitir muchas plataformas, lenguajes de programación y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c62c4-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="c62c4-108">**Estables**: las bibliotecas. NET de buena calidad deben coexistir en el ecosistema de .NET y ejecutarse en aplicaciones que se han compilado mediante muchas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c62c4-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="c62c4-109">**Diseñadas para evolucionar**: las bibliotecas .NET deben mejorar y evolucionar a lo largo del tiempo, a la vez que deben ser compatibles para los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="c62c4-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="c62c4-110">**Depurables**: las bibliotecas .NET deben usar las herramientas más recientes para ofrecer una buena experiencia de depuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c62c4-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="c62c4-111">**Confiables**: las bibliotecas .NET ganan la confianza de los desarrolladores publicando en NuGet de acuerdo con los procedimientos recomendados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c62c4-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c62c4-112">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="c62c4-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="c62c4-113">Tipos de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c62c4-113">Types of recommendations</span></span>

<span data-ttu-id="c62c4-114">Cada artículo presenta cuatro tipos de recomendaciones: **Debe**, **Es recomendable**, **Evite** y **No está permitido**.</span><span class="sxs-lookup"><span data-stu-id="c62c4-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="c62c4-115">El tipo de recomendación indica hasta qué punto se deben seguir.</span><span class="sxs-lookup"><span data-stu-id="c62c4-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="c62c4-116">Casi siempre debe seguir una recomendación **Debe**.</span><span class="sxs-lookup"><span data-stu-id="c62c4-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="c62c4-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c62c4-117">For example:</span></span>

<span data-ttu-id="c62c4-118">**✔️ DEBE** distribuir las bibliotecas mediante un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="c62c4-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="c62c4-119">Por otro lado, las recomendaciones de tipo **Es recomendable** generalmente deben seguirse, pero existen una serie de excepciones legítimas, por lo que no pasa nada si no sigue alguna de ellas:</span><span class="sxs-lookup"><span data-stu-id="c62c4-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="c62c4-120">**✔️ ES RECOMENDABLE** usar [SemVer 2.0.0](https://semver.org/) para crear versiones de los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="c62c4-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="c62c4-121">Las recomendaciones de tipo **Evite** mencionan prácticas que, en general, no son convenientes, aunque a veces tiene sentido no seguirlas:</span><span class="sxs-lookup"><span data-stu-id="c62c4-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="c62c4-122">**❌EVITE** las referencias de paquetes NuGet que requieren una versión exacta.</span><span class="sxs-lookup"><span data-stu-id="c62c4-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="c62c4-123">Y, por último, las recomendaciones de tipo **No está permitido** indican qué no se puede hacer casi nunca:</span><span class="sxs-lookup"><span data-stu-id="c62c4-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="c62c4-124">**❌ NO** publique versiones de la biblioteca tanto con nombre seguro como sin él.</span><span class="sxs-lookup"><span data-stu-id="c62c4-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="c62c4-125">Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="c62c4-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="c62c4-126">Siguiente</span><span class="sxs-lookup"><span data-stu-id="c62c4-126">Next</span></span>](get-started.md)
