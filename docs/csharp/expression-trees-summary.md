---
title: Resumen de árboles de expresión
description: Se resume cómo puede usar árboles de expresión para crear programas dinámicos que interpretan el código como datos y crean nuevas funciones basadas en ese código.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 513244a987e295c81cfb5d00d9a0cfd6912074e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79145896"
---
# <a name="expression-trees-summary"></a><span data-ttu-id="60c4a-103">Resumen de árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="60c4a-103">Expression Trees Summary</span></span>

[<span data-ttu-id="60c4a-104">Anterior: Traducción de expresiones</span><span class="sxs-lookup"><span data-stu-id="60c4a-104">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="60c4a-105">En esta serie, se vio cómo se pueden usar *árboles de expresión* para crear programas dinámicos que interpretan el código como datos y crean nueva funcionalidad basada en ese código.</span><span class="sxs-lookup"><span data-stu-id="60c4a-105">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="60c4a-106">Se pueden examinar los árboles de expresión para entender el propósito de un algoritmo.</span><span class="sxs-lookup"><span data-stu-id="60c4a-106">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="60c4a-107">No se puede examinar solo ese código.</span><span class="sxs-lookup"><span data-stu-id="60c4a-107">You can not only examine that code.</span></span> <span data-ttu-id="60c4a-108">Se pueden crear árboles de expresión nuevos que representen las versiones modificadas del código original.</span><span class="sxs-lookup"><span data-stu-id="60c4a-108">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="60c4a-109">También se pueden usar árboles de expresión para buscar en un algoritmo y traducirlo a otro lenguaje o entorno.</span><span class="sxs-lookup"><span data-stu-id="60c4a-109">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span>

## <a name="limitations"></a><span data-ttu-id="60c4a-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="60c4a-110">Limitations</span></span>

<span data-ttu-id="60c4a-111">Hay algunos elementos de lenguaje de C# nuevos que no se traducen correctamente en árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="60c4a-111">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="60c4a-112">Los árboles de expresión no pueden contener expresiones `await` ni expresiones lambda `async`.</span><span class="sxs-lookup"><span data-stu-id="60c4a-112">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="60c4a-113">Muchas de las características agregadas en la versión 6 de C# no aparecen tal y como se escriben en árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="60c4a-113">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="60c4a-114">En su lugar, se expondrán las características más recientes de los árboles de expresión en la sintaxis equivalente anterior.</span><span class="sxs-lookup"><span data-stu-id="60c4a-114">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="60c4a-115">Es posible que esta limitación no sea tanta como podría parecer.</span><span class="sxs-lookup"><span data-stu-id="60c4a-115">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="60c4a-116">De hecho, significa que el código que interpreta los árboles de expresión probablemente funcionará igual cuando se introduzcan las nuevas características de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="60c4a-116">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="60c4a-117">Incluso con estas limitaciones, los árboles de expresión permiten crear algoritmos dinámicos que se basan en la interpretación y la modificación del código que se representa como una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="60c4a-117">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represented as a data structure.</span></span> <span data-ttu-id="60c4a-118">Es una herramienta eficaz y es una de las características del ecosistema .NET que permite que las bibliotecas enriquecidas como Entity Framework realicen lo que hacen.</span><span class="sxs-lookup"><span data-stu-id="60c4a-118">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>
