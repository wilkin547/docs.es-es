---
title: "invalidMemberDeclaration MDA | Microsoft Docs"
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
  - "invalid member declaration"
  - "InvalidMemberDeclaration MDA"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# invalidMemberDeclaration MDA
El asistente para la depuración administrada \(MDA\) de `invalidMemberDeclaration` se activa para informar acerca de un error que se produce a la hora de determinar cómo calcular las referencias de los parámetros de un miembro al que se va a llamar desde COM.  
  
## Síntomas  
 Se devuelve a COM un valor HRESULT de error sin que se haya llamado al método administrado.  
  
## Motivo  
 Esto probablemente se debe a un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatible en uno de los parámetros.  
  
## Solución  
 Especifique los atributos <xref:System.Runtime.InteropServices.MarshalAsAttribute> válidos en los parámetros.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## Resultado  
 Mensaje informativo que contiene el nombre de miembro, el nombre de tipo y el mensaje de error.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)