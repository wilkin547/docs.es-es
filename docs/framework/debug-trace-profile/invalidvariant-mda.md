---
title: "invalidVariant MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid variant"
  - "VARIANT type errors"
  - "InvalidVariant MDA"
  - "invalid VARIANT types"
  - "managed debugging assistants (MDAs), invalid variant"
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# invalidVariant MDA
El asistente para la depuración administrada \(MDA\) de `invalidVariant` se activa cuando se encuentra una estructura `VARIANT` no válida durante una llamada de código nativo o no administrado a un código administrado.  
  
## Síntomas  
 Comportamiento inesperado durante una transición entre código nativo y administrado que implica el cálculo de referencias de `VARIANT` a un objeto.  
  
## Motivo  
 El código nativo está pasando una estructura `VARIANT` incorrecta al código administrado.   El motor en tiempo de ejecución intenta calcular las referencias de `VARIANT` a un objeto y activa el MDA si `VARIANT` no es válido.  Los ejemplos de `VARIANT` no válida incluyen `VARIANT` con `VARTYPE` VT\_EMPTY &#124; VT\_BYREF o `VARIANT` con `VARTYPE` VT\_VARIANT.  
  
## Resolución  
 El paso de `VARIANT` por parte del código nativo o no administrado debe garantizar que `VARIANT` se forme e inicialice correctamente.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.  
  
## Resultado  
 Un mensaje de MDA que indica que el motor en tiempo de ejecución detectó una `VARIANT` no válida pasada a código administrado mediante un módulo no administrado.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)