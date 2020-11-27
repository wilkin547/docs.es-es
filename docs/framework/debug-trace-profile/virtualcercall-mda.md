---
title: MDA de virtualCERCall
description: Revise el Asistente para la depuración administrada (MDA) de virtualCERCall, que se invoca si una CER contiene una llamada a un método virtual que no se puede preparar automáticamente.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
ms.openlocfilehash: c3e8060702239c6f87659f48658160e46491542f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257098"
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="5db22-103">MDA de virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="5db22-103">virtualCERCall MDA</span></span>

<span data-ttu-id="5db22-104">El Asistente para la depuración administrada (MDA) `virtualCERCall` se activa como una advertencia que indica que un sitio de llamada dentro de un gráfico de llamadas de región de ejecución restringida (CER) hace referencia a un destino virtual, es decir, una llamada virtual a un método virtual no final o una llamada mediante una interfaz.</span><span class="sxs-lookup"><span data-stu-id="5db22-104">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="5db22-105">El Common Language Runtime (CLR) no puede predecir el método de destino de estas llamadas solo con el lenguaje intermedio y el análisis de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5db22-105">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="5db22-106">Como resultado, el árbol de llamadas no se puede preparar como parte del gráfico de CER y las anulaciones de subprocesos de ese subárbol no se pueden bloquear automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5db22-106">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="5db22-107">Este MDA advierte de los casos en los que es posible que se tenga que ampliar una CER mediante llamadas explícitas al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> una vez que la información adicional necesaria para calcular el destino de la llamada se conoce en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5db22-107">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5db22-108">Síntomas</span><span class="sxs-lookup"><span data-stu-id="5db22-108">Symptoms</span></span>  

 <span data-ttu-id="5db22-109">Las CER que no se ejecutan cuando se anula un subproceso o se descarga un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5db22-109">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5db22-110">Causa</span><span class="sxs-lookup"><span data-stu-id="5db22-110">Cause</span></span>  

 <span data-ttu-id="5db22-111">Una CER contiene una llamada a un método virtual que no se puede preparar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5db22-111">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5db22-112">Solución</span><span class="sxs-lookup"><span data-stu-id="5db22-112">Resolution</span></span>  

 <span data-ttu-id="5db22-113">Llame a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> para el método virtual.</span><span class="sxs-lookup"><span data-stu-id="5db22-113">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5db22-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="5db22-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="5db22-115">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="5db22-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5db22-116">Resultados</span><span class="sxs-lookup"><span data-stu-id="5db22-116">Output</span></span>  
  
```output
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="5db22-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="5db22-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="5db22-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5db22-118">Example</span></span>  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5db22-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5db22-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5db22-120">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="5db22-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5db22-121">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="5db22-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
