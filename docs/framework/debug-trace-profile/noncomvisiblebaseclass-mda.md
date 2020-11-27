---
title: MDA de nonComVisibleBaseClass
description: Vea el Asistente para la depuración administrada (MDA) de nonComVisibleBaseClass, que se invoca en llamadas QueryInterface desde código nativo con errores COR_E_INVALIDOPERATION.
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: c13d05d04c75d6b4f1be4a5f338fd7246fed8db4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254576"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="f39cc-103">MDA de nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="f39cc-103">nonComVisibleBaseClass MDA</span></span>

<span data-ttu-id="f39cc-104">El Asistente para la depuración administrada (MDA) `nonComVisibleBaseClass` se activa cuando se realiza una llamada a `QueryInterface` desde código no administrado o nativo en el contenedor CCW de una clase administrada visible para COM que deriva de una clase base que no es visible para COM.</span><span class="sxs-lookup"><span data-stu-id="f39cc-104">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="f39cc-105">La llamada a `QueryInterface` hace que el MDA se active solo cuando la llamada solicita la interfaz de clase o la interfaz predeterminado `IDispatch` de la clase administrada visible para COM.</span><span class="sxs-lookup"><span data-stu-id="f39cc-105">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="f39cc-106">El MDA no se activa cuando `QueryInterface` es para una interfaz explícita que tiene aplicado el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> y se implementa explícitamente la clase visible para COM.</span><span class="sxs-lookup"><span data-stu-id="f39cc-106">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f39cc-107">Síntomas</span><span class="sxs-lookup"><span data-stu-id="f39cc-107">Symptoms</span></span>  

 <span data-ttu-id="f39cc-108">Una llamada a `QueryInterface` que se realiza desde código nativo produce el error COR_E_INVALIDOPERATION HRESULT.</span><span class="sxs-lookup"><span data-stu-id="f39cc-108">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="f39cc-109">El HRESULT podría deberse a que CLR no permite llamadas a  `QueryInterface` que producirían la activación de este MDA.</span><span class="sxs-lookup"><span data-stu-id="f39cc-109">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f39cc-110">Causa</span><span class="sxs-lookup"><span data-stu-id="f39cc-110">Cause</span></span>  

 <span data-ttu-id="f39cc-111">CLR no puede permitir llamadas a `QueryInterface` para la interfaz de clase o la interfaz `IDispatch` predeterminada de una clase visible para COM que deriva de una clase que no es visible para COM debido a posibles problemas de versiones.</span><span class="sxs-lookup"><span data-stu-id="f39cc-111">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="f39cc-112">Por ejemplo, si se agregan miembros públicos a la clase base que no es visible para COM, los clientes COM existentes que usan la clase derivada podrían interrumpirse porque la vtable de la clase derivada, que contiene los miembros de clase base, se vería alterada por ese cambio.</span><span class="sxs-lookup"><span data-stu-id="f39cc-112">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="f39cc-113">Las interfaces explícitas expuestas a COM no tienen este problema porque no incluyen los miembros base de las interfaces en la vtable.</span><span class="sxs-lookup"><span data-stu-id="f39cc-113">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f39cc-114">Solución</span><span class="sxs-lookup"><span data-stu-id="f39cc-114">Resolution</span></span>  

 <span data-ttu-id="f39cc-115">No exponga la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="f39cc-115">Do not expose the class interface.</span></span> <span data-ttu-id="f39cc-116">Defina una interfaz explícita y aplíquele el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f39cc-116">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f39cc-117">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="f39cc-117">Effect on the Runtime</span></span>  

 <span data-ttu-id="f39cc-118">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="f39cc-118">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f39cc-119">Resultados</span><span class="sxs-lookup"><span data-stu-id="f39cc-119">Output</span></span>  

 <span data-ttu-id="f39cc-120">El siguiente es un mensaje de ejemplo de una llamada a `QueryInterface` en una clase visible para COM `Derived` que deriva de una clase no visible para COM `Base`.</span><span class="sxs-lookup"><span data-stu-id="f39cc-120">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM
visible managed class 'Derived'. However since this class derives from
non COM visible class 'Base', the QueryInterface call will fail. This
is done to prevent the non COM visible base class from being
constrained by the COM versioning rules.
```  
  
## <a name="configuration"></a><span data-ttu-id="f39cc-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="f39cc-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f39cc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f39cc-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f39cc-123">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="f39cc-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f39cc-124">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f39cc-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
