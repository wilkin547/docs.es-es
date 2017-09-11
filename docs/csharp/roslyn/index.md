---
title: "Uso del SDK del compilador de .NET - Guía de C#"
description: "Explore las API de Roslyn para crear correcciones de código y diagnósticos automáticos"
keywords: .NET, .NET Core, C#, Roslyn,
ms.date: 06/25/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: abed9e00-2ddc-468e-9cca-d033bd6a7e36
redirect_url: /dotnet/csharp/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b227d67fd5431da328e1686fd9afc6a3b9db035e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="-using-the-net-compiler-sdk"></a><span data-ttu-id="1a73a-104">🔧 Uso del SDK del compilador de .NET</span><span class="sxs-lookup"><span data-stu-id="1a73a-104">🔧 Using the .NET Compiler SDK</span></span>

> <span data-ttu-id="1a73a-105">**Nota:**</span><span class="sxs-lookup"><span data-stu-id="1a73a-105">**Note**</span></span>
> 
> <span data-ttu-id="1a73a-106">¡Este tema no se ha escrito todavía!</span><span class="sxs-lookup"><span data-stu-id="1a73a-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="1a73a-107">Le agradecemos sus comentarios para facilitar el ámbito y el enfoque.</span><span class="sxs-lookup"><span data-stu-id="1a73a-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="1a73a-108">Puede hacer un seguimiento del estado de este [asunto](https://github.com/dotnet/docs/issues/972) y brindar comentarios al respecto en GitHub.</span><span class="sxs-lookup"><span data-stu-id="1a73a-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/972) at GitHub.</span></span>
> 
> <span data-ttu-id="1a73a-109">Si desea revisar esquemas y borradores iniciales de este tema, deje una nota con su información de contacto en el asunto.</span><span class="sxs-lookup"><span data-stu-id="1a73a-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="1a73a-110">Más información sobre cómo puede contribuir en [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="1a73a-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

<span data-ttu-id="1a73a-111">Se trata de un tema de metadatos de una sección completa.</span><span class="sxs-lookup"><span data-stu-id="1a73a-111">This is a meta-topic for an entire section.</span></span> <span data-ttu-id="1a73a-112">Las áreas que deben tratarse aquí incluyen:</span><span class="sxs-lookup"><span data-stu-id="1a73a-112">Areas that need to be covered here include:</span></span> 
* <span data-ttu-id="1a73a-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="1a73a-113">Getting Started</span></span>
* <span data-ttu-id="1a73a-114">Ejemplos y tutoriales</span><span class="sxs-lookup"><span data-stu-id="1a73a-114">Samples and tutorials</span></span>
* <span data-ttu-id="1a73a-115">Contenido conceptual</span><span class="sxs-lookup"><span data-stu-id="1a73a-115">conceptual content</span></span>
* <span data-ttu-id="1a73a-116">Modelo general de las API</span><span class="sxs-lookup"><span data-stu-id="1a73a-116">overall model of the APIs</span></span>
* <span data-ttu-id="1a73a-117">Vínculos a ejemplos en el repositorio [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers)</span><span class="sxs-lookup"><span data-stu-id="1a73a-117">links to samples on the [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) repository</span></span>
* <span data-ttu-id="1a73a-118">Vínculos a otro contenido de referencia</span><span class="sxs-lookup"><span data-stu-id="1a73a-118">links to other reference content</span></span>

