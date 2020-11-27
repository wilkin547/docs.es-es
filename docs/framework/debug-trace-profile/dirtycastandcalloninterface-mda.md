---
title: MDA de dirtyCastAndCallOnInterface
description: Revise el Asistente para la depuración administrada de dirtyCastAndCallOnInterface, que se invoca cuando las llamadas de vtable enlazadas en tiempo de compilación se realizan en interfaces de clase solo enlazadas en tiempo de ejecución.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
ms.openlocfilehash: 49a2930d91e76856436480512360e8b9f9fd3d7a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273586"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="0c869-103">MDA de dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="0c869-103">dirtyCastAndCallOnInterface MDA</span></span>

<span data-ttu-id="0c869-104">El Asistente para la depuración administrada (MDA) `dirtyCastAndCallOnInterface` se activa cuando se intenta realizar una llamada enlazada en tiempo de compilación a través de una vtable en una interfaz de clase que se ha marcado solo como enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c869-104">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0c869-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0c869-105">Symptoms</span></span>  

 <span data-ttu-id="0c869-106">Una aplicación produce una infracción de acceso o tiene un comportamiento inesperado cuando se realiza una llamada enlazada en tiempo de compilación a CLR a través de COM.</span><span class="sxs-lookup"><span data-stu-id="0c869-106">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0c869-107">Causa</span><span class="sxs-lookup"><span data-stu-id="0c869-107">Cause</span></span>  

 <span data-ttu-id="0c869-108">El código intenta realizar una llamada enlazada en tiempo de compilación a través de una vtable mediante una interfaz de clase que es solo enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c869-108">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="0c869-109">Tenga en cuenta que las interfaces de clase predeterminadas se identifican solo como enlazadas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c869-109">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="0c869-110">También pueden identificarse como enlazadas en tiempo de ejecución cuando el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> tiene un valor <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span><span class="sxs-lookup"><span data-stu-id="0c869-110">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0c869-111">Solución</span><span class="sxs-lookup"><span data-stu-id="0c869-111">Resolution</span></span>  

 <span data-ttu-id="0c869-112">La solución recomendada es definir una interfaz explícita para que COM la use y hacer que los clientes COM llamen a través de esta interfaz en lugar de la interfaz de clase que se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0c869-112">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="0c869-113">Como alternativa, la llamada desde COM se puede transformar en una llamada enlazada en tiempo de ejecución mediante `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="0c869-113">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="0c869-114">Por último, es posible identificar la clase como <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) para permitir que se realicen llamadas enlazadas en tiempo de compilación desde COM; sin embargo, se desaconseja usar <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> debido a las limitaciones del control de versiones descritas en <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0c869-114">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0c869-115">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="0c869-115">Effect on the Runtime</span></span>  

 <span data-ttu-id="0c869-116">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="0c869-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="0c869-117">Solo notifica datos sobre las llamadas enlazadas en tiempo de compilación en interfaces enlazadas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c869-117">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0c869-118">Resultados</span><span class="sxs-lookup"><span data-stu-id="0c869-118">Output</span></span>  

 <span data-ttu-id="0c869-119">El nombre del método o el nombre del campo al que se va a acceder mediante enlace en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0c869-119">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0c869-120">Configuración</span><span class="sxs-lookup"><span data-stu-id="0c869-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c869-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c869-121">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="0c869-122">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="0c869-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
