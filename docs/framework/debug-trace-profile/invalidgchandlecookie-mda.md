---
title: "invalidGCHandleCookie MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid cookies"
  - "cookies, invalid"
  - "managed debugging assistants (MDAs), invalid cookies"
  - "InvalidGCHandleCookie MDA"
  - "invalid cookies"
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# invalidGCHandleCookie MDA
El asistente para la depuración administrada \(MDA\) `invalidGCHandleCookie` se activa cuando se intenta una conversión de una cookie <xref:System.IntPtr> no válida en <xref:System.Runtime.InteropServices.GCHandle>.  
  
## Síntomas  
 Comportamiento indefinido, como infracciones de acceso y daños en la memoria, al intentar utilizar o recuperar un <xref:System.Runtime.InteropServices.GCHandle> de un <xref:System.IntPtr>.  
  
## Motivo  
 Probablemente la cookie no sea válida porque no fue creada originalmente a partir de un <xref:System.Runtime.InteropServices.GCHandle>, porque representa un <xref:System.Runtime.InteropServices.GCHandle> que ya ha sido liberado, porque es una cookie a un objeto <xref:System.Runtime.InteropServices.GCHandle> de otro dominio de aplicación o porque se calcularon las referencias a código nativo como <xref:System.Runtime.InteropServices.GCHandle>, pero se volvió a pasar a CLR como <xref:System.IntPtr>, donde se intentó una conversión.  
  
## Resolución  
 Especifique una cookie <xref:System.IntPtr> válida para <xref:System.Runtime.InteropServices.GCHandle>.  
  
## Efecto en el Runtime  
 Cuando se habilita el asistente para la depuración administrada, el depurador ya no puede seguir realizando el seguimiento de las raíces y sus objetos, porque los valores pasados de la cookie son distintos de los devueltos cuando el asistente para la depuración administrada no está habilitado.  
  
## Resultados  
 Se crea un informe con el valor de la cookie <xref:System.IntPtr> no válida.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>   
 <xref:System.Runtime.InteropServices.GCHandle>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)