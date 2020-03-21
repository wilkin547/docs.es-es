---
title: Funciones de devolución de llamada
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: 8b8bb4dff4f73247282060c0b4fd778ae0169b1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181517"
---
# <a name="callback-functions"></a><span data-ttu-id="4de7f-102">Funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="4de7f-102">Callback Functions</span></span>
<span data-ttu-id="4de7f-103">Una función de devolución de llamada es código dentro de una aplicación administrada que ayuda a una función DLL no administrada a completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="4de7f-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="4de7f-104">Las llamadas a una función de devolución de llamada pasan indirectamente desde una aplicación administrada, a través de una función DLL, y de nuevo a la implementación administrada.</span><span class="sxs-lookup"><span data-stu-id="4de7f-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="4de7f-105">Algunas de las muchas funciones DLL que se llaman con la invocación de plataforma requieren una función de devolución de llamada en código administrado para ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="4de7f-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="4de7f-106">Para llamar a la mayoría de las funciones DLL desde el código administrado, se crea una definición administrada de la función y, después, se llama.</span><span class="sxs-lookup"><span data-stu-id="4de7f-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="4de7f-107">El proceso es sencillo.</span><span class="sxs-lookup"><span data-stu-id="4de7f-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="4de7f-108">El uso de una función DLL que requiere una función de devolución de llamada tiene algunos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="4de7f-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="4de7f-109">En primer lugar, se debe determinar si la función requiere una devolución de llamada examinando la documentación de la función.</span><span class="sxs-lookup"><span data-stu-id="4de7f-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="4de7f-110">Después, habrá que crear la función de devolución de llamada en la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="4de7f-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="4de7f-111">Por último, se llama a la función DLL, pasando un puntero a la función de devolución de llamada como argumento.</span><span class="sxs-lookup"><span data-stu-id="4de7f-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="4de7f-112">En la siguiente ilustración se resumen la función de devolución de llamada y los pasos de implementación:</span><span class="sxs-lookup"><span data-stu-id="4de7f-112">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Diagrama que muestra el proceso de devolución de llamada para la invocación de plataforma.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="4de7f-114">Las funciones de devolución de llamada son ideales para su uso en situaciones en las que se realiza una tarea repetidamente.</span><span class="sxs-lookup"><span data-stu-id="4de7f-114">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="4de7f-115">Otro uso frecuente es con funciones de enumeración, como **EnumFontFamilies**, **EnumPrinters** y **EnumWindows** en la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="4de7f-115">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="4de7f-116">La función **EnumWindows** enumera todas las ventanas existentes en el equipo, y llama a la función de devolución de llamada para realizar una tarea en cada ventana.</span><span class="sxs-lookup"><span data-stu-id="4de7f-116">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="4de7f-117">Para obtener instrucciones y un ejemplo, vea [Cómo: Implementar funciones de devolución de llamada](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="4de7f-117">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de7f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4de7f-118">See also</span></span>

- [<span data-ttu-id="4de7f-119">Cómo: Implementar funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="4de7f-119">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="4de7f-120">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="4de7f-120">Calling a DLL Function</span></span>](calling-a-dll-function.md)
