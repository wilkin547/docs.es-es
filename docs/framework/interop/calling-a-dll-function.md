---
title: Llamar a una función DLL
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 14589544e05f6c59f4f58f7723fef40e75af9823
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123715"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="01388-102">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="01388-102">Calling a DLL Function</span></span>
<span data-ttu-id="01388-103">Aunque llamar a funciones DLL no administradas es prácticamente idéntico a llamar a otro código administrado, hay diferencias que pueden hacer que las funciones DLL parezcan confusas al principio.</span><span class="sxs-lookup"><span data-stu-id="01388-103">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="01388-104">En esta sección se presentan temas que describen algunos de los problemas inusuales relacionados con las llamadas.</span><span class="sxs-lookup"><span data-stu-id="01388-104">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="01388-105">Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos de datos que tengan la misma representación en código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="01388-105">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="01388-106">Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión (vea [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="01388-106">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="01388-107">Para llamar a una función que tiene una estructura que no puede transferirse en bloque de bits como su tipo de valor devuelto, se puede definir un tipo del asistente que pueda transferirse en bloque de bits del mismo tamaño que el tipo que no puede transferirse en bloque de bits y convertir los datos después de que la función devuelva un resultado.</span><span class="sxs-lookup"><span data-stu-id="01388-107">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01388-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="01388-108">In This Section</span></span>  
 [<span data-ttu-id="01388-109">Pasar estructuras</span><span class="sxs-lookup"><span data-stu-id="01388-109">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="01388-110">Identifica los problemas de pasar estructuras de datos con un diseño predefinido.</span><span class="sxs-lookup"><span data-stu-id="01388-110">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="01388-111">Funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="01388-111">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="01388-112">Proporciona información básica sobre las funciones de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="01388-112">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="01388-113">Cómo: Implementar funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="01388-113">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="01388-114">Describe cómo implementar funciones de devolución de llamada en código administrado.</span><span class="sxs-lookup"><span data-stu-id="01388-114">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="01388-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="01388-115">Related Sections</span></span>  
 [<span data-ttu-id="01388-116">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="01388-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="01388-117">Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="01388-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="01388-118">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="01388-118">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="01388-119">Describe cómo se declaran parámetros de método y se pasan argumentos a funciones exportadas por bibliotecas no administradas.</span><span class="sxs-lookup"><span data-stu-id="01388-119">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
