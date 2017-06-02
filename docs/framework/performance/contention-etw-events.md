---
title: "Contention ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "contention events [.NET Framework]"
  - "ETW, contention events (CLR)"
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Contention ETW Events
Los eventos de contención se generan siempre que haya una contención para bloqueos <xref:System.Threading.Monitor?displayProperty=fullName> o para bloqueos nativos utilizados por el runtime.  La contención se produce cuando un subproceso está esperando a un bloqueo mientras ese bloqueo está en posesión de otro subproceso.  
  
 En la siguiente tabla se muestra la palabra clave con la que se generan los eventos de contención, así como el nivel de los eventos. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`ContentionKeyword` \(0x4000\)|Informativo \(4\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Identificador de evento|Se genera cuando|  
|------------|-----------------------------|----------------------|  
|`ContentionStart_V1`|81|Se inicia la contención.  Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso espere para adquirir un bloqueo; solo se genera cuando el subproceso está esperando para adquirir un bloqueo.|  
|`ContentionStop`|81|Finaliza la contención.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|Marcas|win:UInt8|0 para administrado; 1 para nativo.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)