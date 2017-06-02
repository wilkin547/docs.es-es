---
title: "marshalCleanupError MDA | Microsoft Docs"
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
  - "cleanup operations"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
  - "marshaling cleanup error"
  - "MarshalCleanupError MDA"
  - "memory, cleanup errors"
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# marshalCleanupError MDA
El asistente para la depuración administrada \(MDA, por sus siglas en inglés\) `marshalCleanupError` se activa cuando Common Language Runtime \(CLR\) detecta un error al intentar limpiar la memoria y las estructuras temporales que se usan para calcular las referencias de tipos de datos entre los límites del código nativo y administrado.  
  
## Síntomas  
 Se produce una pérdida de memoria al realizar transiciones de código nativo y administrado, cuando no se restaura un estado de runtime \(por ejemplo, una referencia cultural de subproceso\) o si la limpieza de <xref:System.Runtime.InteropServices.SafeHandle> tiene errores.  
  
## Motivo  
 Se produjo un error inesperado al limpiar las estructuras temporales.  
  
## Solución  
 Revise todas las implementaciones de destructor, finalizador y cálculo de referencias de <xref:System.Runtime.InteropServices.SafeHandle> para comprobar si hay errores.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## Salida  
 Un mensaje que indica que se produjo un error en la operación durante la limpieza.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)