---
title: Llamar a una función DLL
description: Revise los problemas relacionados con la llamada a una función DLL que puede parecer confusa. El proceso de llamada de función difiere en función de si el tipo de valor devuelto se puede transferir en bloque de bits.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 90f8f47148e652a9942a35be1564bed94c155216
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620903"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="1eade-104">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="1eade-104">Calling a DLL Function</span></span>
<span data-ttu-id="1eade-105">Aunque llamar a funciones DLL no administradas es prácticamente idéntico a llamar a otro código administrado, hay diferencias que pueden hacer que las funciones DLL parezcan confusas al principio.</span><span class="sxs-lookup"><span data-stu-id="1eade-105">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="1eade-106">En esta sección se presentan temas que describen algunos de los problemas inusuales relacionados con las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1eade-106">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="1eade-107">Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos de datos que tengan la misma representación en código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="1eade-107">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="1eade-108">Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión (vea [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="1eade-108">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="1eade-109">Para llamar a una función que tiene una estructura que no puede transferirse en bloque de bits como su tipo de valor devuelto, se puede definir un tipo del asistente que pueda transferirse en bloque de bits del mismo tamaño que el tipo que no puede transferirse en bloque de bits y convertir los datos después de que la función devuelva un resultado.</span><span class="sxs-lookup"><span data-stu-id="1eade-109">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1eade-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1eade-110">In This Section</span></span>  
 [<span data-ttu-id="1eade-111">Pasar estructuras</span><span class="sxs-lookup"><span data-stu-id="1eade-111">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="1eade-112">Identifica los problemas de pasar estructuras de datos con un diseño predefinido.</span><span class="sxs-lookup"><span data-stu-id="1eade-112">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="1eade-113">Funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="1eade-113">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="1eade-114">Proporciona información básica sobre las funciones de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1eade-114">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="1eade-115">Cómo: Implementar funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="1eade-115">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="1eade-116">Describe cómo implementar funciones de devolución de llamada en código administrado.</span><span class="sxs-lookup"><span data-stu-id="1eade-116">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1eade-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1eade-117">Related Sections</span></span>  
 [<span data-ttu-id="1eade-118">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="1eade-118">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="1eade-119">Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="1eade-119">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="1eade-120">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="1eade-120">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="1eade-121">Describe cómo se declaran parámetros de método y se pasan argumentos a funciones exportadas por bibliotecas no administradas.</span><span class="sxs-lookup"><span data-stu-id="1eade-121">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
