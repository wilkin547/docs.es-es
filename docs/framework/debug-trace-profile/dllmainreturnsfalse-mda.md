---
title: MDA de dllMainReturnsFalse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb5de2b1c41d102fbf9fc47db0ff3d8bd72a3bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="0a58b-102">MDA de dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="0a58b-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="0a58b-103">El asistente para la depuración administrada (MDA) `dllMainReturnsFalse` se activa si la función administrada `DllMain` de un ensamblado de usuario denominado con la razón DLL_PROCESS_ATTACH devuelve FALSE.</span><span class="sxs-lookup"><span data-stu-id="0a58b-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0a58b-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0a58b-104">Symptoms</span></span>  
 <span data-ttu-id="0a58b-105">La función `DllMain` devuelve FALSE, lo que indica que no se ha ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a58b-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="0a58b-106">Esto puede causar problemas indeterminados, ya que las funciones `DllMain` normalmente contienen código de inicialización importante.</span><span class="sxs-lookup"><span data-stu-id="0a58b-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0a58b-107">Motivo</span><span class="sxs-lookup"><span data-stu-id="0a58b-107">Cause</span></span>  
 <span data-ttu-id="0a58b-108">La función `DllMain` se denomina con la razón DLL_PROCESS_ATTACH para la inicialización del archivo DLL tras la carga.</span><span class="sxs-lookup"><span data-stu-id="0a58b-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="0a58b-109">Si devuelve FALSE, significa que se ha producido un error en la inicialización del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="0a58b-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0a58b-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="0a58b-110">Resolution</span></span>  
 <span data-ttu-id="0a58b-111">Analice el código de la función `DllMain` del archivo DLL erróneo e identifique la causa del error de inicialización.</span><span class="sxs-lookup"><span data-stu-id="0a58b-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0a58b-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="0a58b-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="0a58b-113">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="0a58b-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="0a58b-114">Solo notifica datos sobre el valor devuelto de `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="0a58b-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0a58b-115">Salida</span><span class="sxs-lookup"><span data-stu-id="0a58b-115">Output</span></span>  
 <span data-ttu-id="0a58b-116">Un mensaje que indica que una función `DllMain`, denominada con la razón DLL_PROCESS_ATTACH, ha devuelto FALSE.</span><span class="sxs-lookup"><span data-stu-id="0a58b-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="0a58b-117">Tenga en cuenta que este MDA solo se activa si `DllMain` se implementa en código administrado.</span><span class="sxs-lookup"><span data-stu-id="0a58b-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0a58b-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="0a58b-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a58b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a58b-119">See Also</span></span>  
 [<span data-ttu-id="0a58b-120">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="0a58b-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
