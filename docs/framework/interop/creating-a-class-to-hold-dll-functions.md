---
title: Crear una clase para contener funciones de archivos DLL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d64034f8059dc094b3fc8a71c6a2b7e96fe8d89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="18bf7-102">Crear una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="18bf7-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="18bf7-103">Encapsular una función DLL que se usa con frecuencia en una clase administrada es un enfoque efectivo para encapsular la funcionalidad de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="18bf7-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="18bf7-104">Aunque no es obligatorio hacerlo en todos los casos, proporcionar un contenedor de clases es cómodo porque la definición de funciones DLL puede ser compleja y propensa a errores.</span><span class="sxs-lookup"><span data-stu-id="18bf7-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="18bf7-105">Si está programando en Visual Basic o C#, debe declarar las funciones DLL dentro de una clase o módulo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18bf7-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="18bf7-106">Dentro de una clase, se define un método estático para cada función DLL que se quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="18bf7-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="18bf7-107">La definición puede incluir información adicional, como el juego de caracteres o la convención de llamada que se usa para pasar argumentos de método; si se omite esta información, se selecciona la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18bf7-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="18bf7-108">Para obtener una lista completa de las opciones de declaración y sus valores predeterminados, vea [Crear prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="18bf7-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="18bf7-109">Una vez encapsulados, puede llamar a métodos en la función como llamaría a los métodos de cualquier otra función estática.</span><span class="sxs-lookup"><span data-stu-id="18bf7-109">Once wrapped, you can call methods on the function as you call methods on any other static function.</span></span> <span data-ttu-id="18bf7-110">La invocación de plataforma controla automáticamente la función exportada subyacente.</span><span class="sxs-lookup"><span data-stu-id="18bf7-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="18bf7-111">Al diseñar una clase administrada para la invocación de plataforma, tenga en cuenta las relaciones entre las clases y las funciones de archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="18bf7-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="18bf7-112">Por ejemplo, se puede:</span><span class="sxs-lookup"><span data-stu-id="18bf7-112">For example, you can:</span></span>  
  
-   <span data-ttu-id="18bf7-113">Declarar funciones DLL dentro de una clase existente.</span><span class="sxs-lookup"><span data-stu-id="18bf7-113">Declare DLL functions within an existing class.</span></span>  
  
-   <span data-ttu-id="18bf7-114">Crear una clase individual para cada función DLL, para mantener las funciones aisladas y facilitar su búsqueda.</span><span class="sxs-lookup"><span data-stu-id="18bf7-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
-   <span data-ttu-id="18bf7-115">Crear una clase para un conjunto de funciones DLL relacionadas para formar grupos lógicos y reducir la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="18bf7-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="18bf7-116">Puede asignar el nombre que quiera a la clase y sus métodos.</span><span class="sxs-lookup"><span data-stu-id="18bf7-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="18bf7-117">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="18bf7-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bf7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="18bf7-118">See Also</span></span>  
 [<span data-ttu-id="18bf7-119">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="18bf7-119">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="18bf7-120">Identificar funciones en archivos DLL</span><span class="sxs-lookup"><span data-stu-id="18bf7-120">Identifying Functions in DLLs</span></span>](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [<span data-ttu-id="18bf7-121">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="18bf7-121">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="18bf7-122">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="18bf7-122">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
