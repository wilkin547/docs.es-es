---
title: Guía de la biblioteca de código abierto
description: Procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374913"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="a5c90-103">Guía de la biblioteca de código abierto</span><span class="sxs-lookup"><span data-stu-id="a5c90-103">Open-source library guidance</span></span>

<span data-ttu-id="a5c90-104">En esta guía se ofrecen procedimientos recomendados para desarrolladores a la hora de crear bibliotecas .NET de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="a5c90-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="a5c90-105">Esta documentación se centra en el *qué* y el *porqué* de la compilación de una biblioteca .NET, no en el *cómo*.</span><span class="sxs-lookup"><span data-stu-id="a5c90-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="a5c90-106">Aspectos de las bibliotecas .NET de código abierto de alta calidad:</span><span class="sxs-lookup"><span data-stu-id="a5c90-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a5c90-107">**Inclusivas**: las bibliotecas. NET de buena calidad deben estar diseñadas para admitir muchas plataformas y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a5c90-107">**Inclusive** - Good .NET libraries strive to support many platforms and applications.</span></span>
> * <span data-ttu-id="a5c90-108">**Estables**: las bibliotecas. NET de buena calidad deben coexistir en el ecosistema de .NET y ejecutarse en aplicaciones que se han compilado mediante muchas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a5c90-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="a5c90-109">**Diseñadas para evolucionar**: las bibliotecas .NET deben mejorar y evolucionar a lo largo del tiempo, a la vez que deben ser compatibles para los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="a5c90-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="a5c90-110">**Depurables**: las bibliotecas .NET deben usar las herramientas más recientes para ofrecer una buena experiencia de depuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a5c90-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="a5c90-111">**Confiables**: las bibliotecas .NET ganan la confianza de los desarrolladores publicando en NuGet de acuerdo con los procedimientos recomendados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a5c90-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a5c90-112">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="a5c90-112">Get Started</span></span>](./get-started.md)

## <a name="recommendations"></a><span data-ttu-id="a5c90-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a5c90-113">Recommendations</span></span>

<span data-ttu-id="a5c90-114">En cada artículo se ofrece una lista de recomendaciones para las bibliotecas .NET mediante las palabras **Debe**, **Es recomendable**, **Evite** y **No está permitido**.</span><span class="sxs-lookup"><span data-stu-id="a5c90-114">With each article, there is a list of recommendations for your .NET library using **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="a5c90-115">Las que se usan en cada recomendación indican hasta qué punto se deben seguir.</span><span class="sxs-lookup"><span data-stu-id="a5c90-115">The wording of each recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="a5c90-116">Las recomendaciones de tipo **Debe** son aquellas que hay que seguir casi siempre:</span><span class="sxs-lookup"><span data-stu-id="a5c90-116">A **Do** recommendation is one that should almost always be followed:</span></span>

<span data-ttu-id="a5c90-117">**✔️ DEBE** distribuir las bibliotecas mediante un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5c90-117">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="a5c90-118">Por otro lado, las recomendaciones de tipo **Es recomendable** generalmente deben seguirse, pero existen una serie de excepciones legítimas, por lo que no pasa nada si no sigue alguna de ellas:</span><span class="sxs-lookup"><span data-stu-id="a5c90-118">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="a5c90-119">**✔️ ES RECOMENDABLE** usar [SemVer 2.0.0](https://semver.org/) para crear versiones de los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5c90-119">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="a5c90-120">Las recomendaciones de tipo **Evite** hacen referencia a prácticas que, en general, no son una buena idea, aunque a veces tiene sentido no seguirlas:</span><span class="sxs-lookup"><span data-stu-id="a5c90-120">**Avoid** recommendations are things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="a5c90-121">**❌ EVITE** las referencias de paquetes NuGet que requieren una versión exacta.</span><span class="sxs-lookup"><span data-stu-id="a5c90-121">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="a5c90-122">Y, por último, las recomendaciones de tipo **No está permitido** indican qué no se puede hacer casi nunca:</span><span class="sxs-lookup"><span data-stu-id="a5c90-122">And finally, **do not** indicates something you should almost never do:</span></span>

<span data-ttu-id="a5c90-123">**❌ NO ESTÁ PERMITIDO** publicar versiones de una biblioteca tanto con nombre seguro como sin él.</span><span class="sxs-lookup"><span data-stu-id="a5c90-123">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="a5c90-124">Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="a5c90-124">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="a5c90-125">Siguiente</span><span class="sxs-lookup"><span data-stu-id="a5c90-125">Next</span></span>](./get-started.md)
