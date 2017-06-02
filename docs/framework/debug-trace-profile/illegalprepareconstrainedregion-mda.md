---
title: "illegalPrepareConstrainedRegion MDA | Microsoft Docs"
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
  - "PrepareConstrainedRegions method"
  - "managed debugging assistants (MDAs), illegal PrepareConstrainedRegions"
  - "try/catch exception handling, managed debugging assistants"
  - "IllegalPrepareConstrainedRegions MDA"
  - "MDAs (managed debugging assistants), illegal PrepareConstrainedRegions"
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# illegalPrepareConstrainedRegion MDA
El asistente para la depuración administrada \(MDA\) `illegalPrepareConstrainedRegion` se activa cuando una llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> no precede directamente a la instrucción `try` del controlador de excepciones.  Esta restricción sólo afecta al ámbito de MSIL, por lo que entre la llamada y la instrucción `try` puede incluirse código que no genere código, como comentarios.  
  
## Síntomas  
 Una región de ejecución restringida \(CER\) nunca se considera como tal, sino como un simple bloque de control de excepciones \(`finally` o `catch`\).  Como consecuencia, una región de este tipo no se ejecutará en caso de que se produzca una condición de falta de memoria o la anulación de un subproceso.  
  
## Motivo  
 No se ha seguido correctamente el modelo de preparación de una región CER.  Se trata de un evento de error.  La llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> que se utiliza para marcar que los controladores de excepciones presentan una región CER en sus bloques `catch`\/`finally`\/`fault`\/`filter` debe utilizarse inmediatamente antes de la instrucción `try`.  
  
## Resolución  
 Asegúrese de que la llamada a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> se produzca inmediatamente antes de la instrucción `try` `` .  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 El MDA muestra el nombre del método que llama al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, el desplazamiento del lenguaje MSIL y un mensaje que indica que la llamada no precede directamente al inicio del bloque try.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra el modelo que hace que se active este MDA.  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)