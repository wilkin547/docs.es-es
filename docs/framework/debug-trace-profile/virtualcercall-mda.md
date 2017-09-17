---
title: MDA de virtualCERCall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 334900cbcc04cb1883b93a6bac17309add9ec159
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="virtualcercall-mda"></a>MDA de virtualCERCall
El Asistente para la depuración administrada (MDA) `virtualCERCall` se activa como una advertencia que indica que un sitio de llamada dentro de un gráfico de llamadas de región de ejecución restringida (CER) hace referencia a un destino virtual, es decir, una llamada virtual a un método virtual no final o una llamada mediante una interfaz. El Common Language Runtime (CLR) no puede predecir el método de destino de estas llamadas solo con el lenguaje intermedio y el análisis de metadatos. Como resultado, el árbol de llamadas no se puede preparar como parte del gráfico de CER y las anulaciones de subprocesos de ese subárbol no se pueden bloquear automáticamente. Este MDA advierte de los casos en los que es posible que se tenga que ampliar una CER mediante llamadas explícitas al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> una vez que la información adicional necesaria para calcular el destino de la llamada se conoce en tiempo de ejecución.  
  
## <a name="symptoms"></a>Síntomas  
 Las CER que no se ejecutan cuando se anula un subproceso o se descarga un dominio de aplicación.  
  
## <a name="cause"></a>Motivo  
 Una CER contiene una llamada a un método virtual que no se puede preparar automáticamente.  
  
## <a name="resolution"></a>Resolución  
 Llame a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> para el método virtual.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultado  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
  
```  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnóstico de errores con asistentes para la depuración administrada](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)

