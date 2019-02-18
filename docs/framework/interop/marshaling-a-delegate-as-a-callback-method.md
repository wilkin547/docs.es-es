---
title: Calcular las referencias de un delegado como un método de devolución de llamada
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
ms.openlocfilehash: 23079343244c8471f9ae5ff0a7613d0d8a84242b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219742"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="f0ea3-102">Calcular las referencias de un delegado como un método de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="f0ea3-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="f0ea3-103">En este ejemplo se muestra cómo pasar delegados a una función no administrada que espera recibir punteros de función.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="f0ea3-104">Un delegado es una clase que puede contener una referencia a un método y equivale a un puntero de función con seguridad de tipos o a una función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ea3-105">Cuando se usa un delegado dentro de una llamada, Common Language Runtime evita la eliminación del delegado por el recolector de elementos no utilizados mientras dure esa llamada.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="f0ea3-106">Pero si la función no administrada almacena el delegado para usarlo al finalizar la llamada, debe impedir manualmente la recolección de elementos no utilizados hasta que finalice la función no administrada con el delegado.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="f0ea3-107">Para más información, vea [HandleRef (ejemplo)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) y [GCHandle (ejemplo)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f0ea3-107">For more information, see the [HandleRef Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) and [GCHandle Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span></span>  
  
 <span data-ttu-id="f0ea3-108">En el ejemplo de devolución de llamada se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="f0ea3-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="f0ea3-109">**TestCallBack** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="f0ea3-110">**TestCallBack2** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="f0ea3-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) es una biblioteca personalizada no administrada que contiene una implementación para las funciones enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="f0ea3-112">En este ejemplo, la clase `LibWrap` contiene prototipos administrados para los métodos `TestCallBack` y `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="f0ea3-113">Ambos métodos pasan un delegado a una función de devolución de llamada como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="f0ea3-114">La firma del delegado debe coincidir con la firma del método al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="f0ea3-115">Por ejemplo, los delegados `FPtr` y `FPtr2` tienen firmas idénticas a las de los métodos `DoSomething` y `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="f0ea3-116">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="f0ea3-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="f0ea3-117">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="f0ea3-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ea3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0ea3-118">See also</span></span>
- <span data-ttu-id="f0ea3-119">[Diversos ejemplos de serialización](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f0ea3-119">[Miscellaneous Marshaling Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span></span>
- <span data-ttu-id="f0ea3-120">[Tipos de datos de invocación de plataforma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ac7ay120(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f0ea3-120">[Platform Invoke Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ac7ay120(v=vs.100))</span></span>
- [<span data-ttu-id="f0ea3-121">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="f0ea3-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
