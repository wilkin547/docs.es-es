---
title: Crear una clase para contener funciones de archivos DLL
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
ms.openlocfilehash: 765d4344553a6e65b930a7bf586a41144d220fc6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123622"
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="2c2c6-102">Crear una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="2c2c6-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="2c2c6-103">Encapsular una función DLL que se usa con frecuencia en una clase administrada es un enfoque efectivo para encapsular la funcionalidad de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="2c2c6-104">Aunque no es obligatorio hacerlo en todos los casos, proporcionar un contenedor de clases es cómodo porque la definición de funciones DLL puede ser compleja y propensa a errores.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="2c2c6-105">Si está programando en Visual Basic o C#, debe declarar las funciones DLL dentro de una clase o módulo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="2c2c6-106">Dentro de una clase, se define un método estático para cada función DLL que se quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="2c2c6-107">La definición puede incluir información adicional, como el juego de caracteres o la convención de llamada que se usa para pasar argumentos de método; si se omite esta información, se selecciona la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="2c2c6-108">Para obtener una lista completa de las opciones de declaración y sus valores predeterminados, vea [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="2c2c6-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="2c2c6-109">Una vez encapsulados, puede llamar a métodos en la clase como llamaría a los métodos estáticos en cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-109">Once wrapped, you can call the methods on the class as you call static methods on any other class.</span></span> <span data-ttu-id="2c2c6-110">La invocación de plataforma controla automáticamente la función exportada subyacente.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="2c2c6-111">Al diseñar una clase administrada para la invocación de plataforma, tenga en cuenta las relaciones entre las clases y las funciones de archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="2c2c6-112">Por ejemplo, se puede:</span><span class="sxs-lookup"><span data-stu-id="2c2c6-112">For example, you can:</span></span>  
  
- <span data-ttu-id="2c2c6-113">Declarar funciones DLL dentro de una clase existente.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-113">Declare DLL functions within an existing class.</span></span>  
  
- <span data-ttu-id="2c2c6-114">Crear una clase individual para cada función DLL, para mantener las funciones aisladas y facilitar su búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
- <span data-ttu-id="2c2c6-115">Crear una clase para un conjunto de funciones DLL relacionadas para formar grupos lógicos y reducir la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="2c2c6-116">Puede asignar el nombre que quiera a la clase y sus métodos.</span><span class="sxs-lookup"><span data-stu-id="2c2c6-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="2c2c6-117">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="2c2c6-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2c6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c2c6-118">See also</span></span>

- [<span data-ttu-id="2c2c6-119">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="2c2c6-119">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="2c2c6-120">Identificar funciones en archivos DLL</span><span class="sxs-lookup"><span data-stu-id="2c2c6-120">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="2c2c6-121">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="2c2c6-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="2c2c6-122">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="2c2c6-122">Calling a DLL Function</span></span>](calling-a-dll-function.md)
