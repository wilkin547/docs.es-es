---
title: "Runtime Information ETW Events | Microsoft Docs"
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
  - "runtime information events [.NET Framework]"
  - "ETW, runtime information events"
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Runtime Information ETW Events
Estos eventos ETW registran información sobre el runtime, incluidos SKU, número de versión, manera en que se activó el runtime, parámetros de línea de comandos con los que se inició, el GUID \(si es aplicable\) y otra información pertinente.  Si hay varios runtime ejecutándose dentro de un proceso, la información proporcionada por estos eventos \(ClrInstanceID\) ayuda a eliminar la ambigüedad entre los runtime.  
  
 En la siguiente tabla se muestran los dos eventos de información de runtime.  Los eventos se pueden generar con cualquier palabra clave o máscara. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Evento|Identificador de evento|Proveedor|Descripción|  
|------------|-----------------------------|---------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Se produce al cargar un runtime.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Enumera los runtime cargados.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
|Sku|win:UInt16|1 – CLR de escritorio.<br /><br /> 2 – CoreCLR.|  
|BclVersion – Major Version|win:UInt16|Versión principal de mscorlib.dll.|  
|BclVersion – Minor Version|win:UInt16|Versión secundaria de mscorlib.dll.|  
|BclVersion – Build Number|win:UInt16|Número de compilación de mscorlib.dll.|  
|BclVersion – QFE|win:UInt16|Número de versión de la revisión de mscorlib.dll.|  
|VMVersion – Major Version|win:UInt16|Versión de clr.dll o coreclr.dll, que depende de SKU.|  
|VMVersion – Minor Version|win:UInt16|Versión secundaria de clr.dll o coreclr.dll, que depende de SKU.|  
|VMVersion – Build Number|win:UInt16|Número de compilación de clr.dll o coreclr.dll.|  
|VMVersion – QFE|win:UInt16|Número de versión de la revisión de clr.dll o coreclr.dll.|  
|StartupFlags|win:UInt32|Marcas de inicio definidas en mscoree.h.|  
|StartupMode|win:UInt8|0x01 \- Ejecutable administrado.<br /><br /> 0x02 \- CLR hospedado.<br /><br /> 0x04 \- Interoperabilidad administrada de C\+\+.<br /><br /> 0x08 \- Activado por COM.<br /><br /> 0x10 \- Otros.|  
|CommandLine|win:UnicodeString|No null solo si StartupMode\=0x01.|  
|ComObjectGUID|win:GUID|No null solo si StartupMode\=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Ruta de acceso al archivo .dll de CLR cargado en el proceso.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)