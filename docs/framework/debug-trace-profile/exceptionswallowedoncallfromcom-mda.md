---
title: "exceptionSwallowedOnCallFromCom MDA | Microsoft Docs"
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
  - "messages, informational"
  - "informational messages"
  - "managed debugging assistants (MDAs), exceptions"
  - "exception handling, managed debugging assistants"
  - "MDAs (managed debugging assistants), exceptions"
  - "ExceptionSwallowedOnCallFromCOM MDA"
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# exceptionSwallowedOnCallFromCom MDA
El asistente para la depuración administrada \(MDA, por sus siglas en inglés\) `exceptionSwallowedOnCallFromCOM` se activa cuando se produce una excepción del código de Common Language Runtime \(CLR\) llamado desde COM a través de un método que no tiene un tipo de resultado HRESULT sin administrar.  
  
## Síntomas  
 Una llamada de COM a un componente administrado devuelve un valor FALSE o 0.  También puede ser que, si el método tiene un tipo de valor devuelto void, no haya indicación de que se produjese una excepción durante la ejecución del método.  En este caso, la excepción se detectará de forma silenciosa y la ejecución regresará al emisor de la llamada COM.  
  
## Motivo  
 Se produjo una excepción, pero no hay ningún modo válido de notificarla.  
  
## Solución  
 Solo tiene carácter informativo, no es necesariamente indicativo de un error.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  Solo recoge los datos sobre excepciones detectadas de forma silenciosa.  
  
## Salida  
 Mensaje informativo que contiene el nombre del método, el nombre del tipo y el mensaje de la excepción.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)