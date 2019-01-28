---
title: Serialización de un delegado como un método de devolución de llamada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2aa999199ddf11a1a2db57b6f7b1dd198b4ea61d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529852"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="adafb-102">Serialización de un delegado como un método de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="adafb-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="adafb-103">En este ejemplo se muestra cómo pasar delegados a una función no administrada que espera recibir punteros de función.</span><span class="sxs-lookup"><span data-stu-id="adafb-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="adafb-104">Un delegado es una clase que puede contener una referencia a un método y equivale a un puntero de función con seguridad de tipos o a una función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="adafb-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adafb-105">Cuando se usa un delegado dentro de una llamada, Common Language Runtime evita la eliminación del delegado por el recolector de elementos no utilizados mientras dure esa llamada.</span><span class="sxs-lookup"><span data-stu-id="adafb-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="adafb-106">Pero si la función no administrada almacena el delegado para usarlo al finalizar la llamada, debe impedir manualmente la recolección de elementos no utilizados hasta que finalice la función no administrada con el delegado.</span><span class="sxs-lookup"><span data-stu-id="adafb-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="adafb-107">Para más información, vea [HandleRef (ejemplo)](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) y [GCHandle (ejemplo)](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="adafb-107">For more information, see the [HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) and [GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span></span>  
  
 <span data-ttu-id="adafb-108">En el ejemplo de devolución de llamada se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="adafb-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="adafb-109">**TestCallBack** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="adafb-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="adafb-110">**TestCallBack2** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="adafb-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="adafb-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) es una biblioteca personalizada no administrada que contiene una implementación para las funciones enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="adafb-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="adafb-112">En este ejemplo, la clase `LibWrap` contiene prototipos administrados para los métodos `TestCallBack` y `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="adafb-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="adafb-113">Ambos métodos pasan un delegado a una función de devolución de llamada como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="adafb-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="adafb-114">La firma del delegado debe coincidir con la firma del método al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="adafb-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="adafb-115">Por ejemplo, los delegados `FPtr` y `FPtr2` tienen firmas idénticas a las de los métodos `DoSomething` y `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="adafb-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="adafb-116">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="adafb-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="adafb-117">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="adafb-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="adafb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="adafb-118">See also</span></span>
- <span data-ttu-id="adafb-119">[Diversos ejemplos de serialización](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="adafb-119">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>
- <span data-ttu-id="adafb-120">[Tipos de datos de invocación de plataforma](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="adafb-120">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>
- [<span data-ttu-id="adafb-121">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="adafb-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
