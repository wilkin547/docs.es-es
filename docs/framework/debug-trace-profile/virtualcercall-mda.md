---
title: "virtualCERCall MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MDAs (managed debugging assistants), CER calls"
  - "virtualCERCall MDA"
  - "virtual CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# virtualCERCall MDA
El asistente para la depuración administrada \(MDA\) `virtualCERCall` se activa como una advertencia que indica que un sitio de llamada situado dentro de un gráfico de llamadas de un área de ejecución restringida \(CER\) hace referencia a un destino virtual, es decir, una llamada virtual a un método virtual no final o una llamada utilizando una interfaz.  Common Language Runtime \(CLR\) no puede predecir el método de destino de estas llamadas exclusivamente a partir del lenguaje intermedio y el análisis de los metadatos.  Como resultado, el árbol de llamadas no se puede preparar como parte del gráfico CER y las anulaciones de subprocesos de ese subárbol no se pueden bloquear automáticamente.  Este MDA advierte de los casos en los que podría ser necesario ampliar una CER mediante llamadas explícitas al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> una vez que se conoce en tiempo de ejecución la información adicional necesaria para calcular el destino de la llamada.  
  
## Síntomas  
 Áreas CER que no se ejecutan cuando se anula un subproceso o se descarga un dominio de aplicación.  
  
## Motivo  
 Una CER contiene una llamada a un método virtual que no se puede preparar automáticamente.  
  
## Resolución  
 Llame a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> para el método virtual.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
  
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
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
  
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
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)