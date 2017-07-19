---
title: "failedQI MDA | Microsoft Docs"
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
  - "failed QueryInterface"
  - "FailedQI MDA"
  - "QueryInterface call failures"
  - "MDAs (managed debugging assistants), failed QueryInterface"
  - "managed debugging assistants (MDAs), failed QueryInterface"
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# failedQI MDA
El asistente para la depuración administrada \(MDA\) `failedQI` se activa cuando Runtime llama a `QueryInterface` en un puntero de interfaz COM en nombre de un contenedor al que se puede llamar en tiempo de ejecución \(RCW\) y la llamada `QueryInterface` falla.  
  
## Síntomas  
 No se puede realizar una conversión en un contenedor RCW o se produce un error inesperado en una llamada a COM desde un contenedor RCW  
  
## Motivo  
  
-   La llamada se realiza desde el contexto equivocado.  
  
-   El servidor proxy registrado no puede realizar la llamada `QueryInterface` porque se intentó realizar en el contexto equivocado.  
  
-   Un servidor proxy propiedad de OLE devolvió un valor HRESULT de error.  
  
## Resolución  
 Consulte la documentación sobre reglas COM recogida en el sitio de MSDN.  
  
## Efecto en el Runtime  
 Si no se puede realizar la llamada `QueryInterface`, el contexto cambia y es necesario volver a intentar realizar la llamada `QueryInterface` para ver si el motivo del error era un contexto incorrecto.  
  
## Resultado  
 El nombre administrado de la interfaz, el GUID de la interfaz y el valor HRESULT del error.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)