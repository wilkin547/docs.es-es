---
title: MDA de pInvokeLog
description: Comprenda el Asistente para la depuración administrada (MDA) pInvokeLog, que se activa para cada firma de invocación de plataforma única que se usa durante la ejecución en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: 05af4e17a91f7c0d8f3576a86d3d784ef6666aed
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803695"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="62572-103">MDA de pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="62572-103">pInvokeLog MDA</span></span>
<span data-ttu-id="62572-104">El Asistente para la depuración administrada (MDA) `pInvokeLog` se activa para cada firma de invocación de plataforma única que se usa durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="62572-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="62572-105">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="62572-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="62572-106">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="62572-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="62572-107">Output</span><span class="sxs-lookup"><span data-stu-id="62572-107">Output</span></span>  
 <span data-ttu-id="62572-108">Un mensaje que indica la firma de invocación de plataforma que se usa durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="62572-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="62572-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="62572-109">Configuration</span></span>  
 <span data-ttu-id="62572-110">Cada elemento coincidente filtra los archivos .dll a los que se realizan llamadas de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="62572-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62572-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="62572-111">See also</span></span>

- [<span data-ttu-id="62572-112">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="62572-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="62572-113">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="62572-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
