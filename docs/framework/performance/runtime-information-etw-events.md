---
title: Eventos ETW de información en tiempo de ejecución
description: Vea eventos ETW de información en tiempo de ejecución, que registran la SKU, el número de versión, cómo se activó el Runtime (incluidos los parámetros de línea de comandos), el GUID, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
ms.openlocfilehash: 385519229bdb76841cdf592d95e96d2288ec5e1a
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474233"
---
# <a name="runtime-information-etw-events"></a>Eventos ETW de información en tiempo de ejecución
Estos eventos ETW registran información sobre el tiempo de ejecución, lo que incluye la SKU, el número de versión, la manera en que se ha activado el tiempo de ejecución, los parámetros de línea de comandos con los que se ha iniciado, el GUID (si está disponible) y otra información relevante. Si se están ejecutando varios tiempos de ejecución dentro de un proceso, la información proporcionada por estos eventos (ClrInstanceID) ayuda a eliminar la ambigüedad de los tiempos de ejecución.  
  
 En la tabla siguiente se muestran los dos eventos de información en tiempo de ejecución. Los eventos se pueden generar bajo cualquier palabra clave o máscara. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Evento|Id. de evento|Proveedor|Descripción|  
|-----------|--------------|--------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Se genera cuando se carga un tiempo de ejecución.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Enumera los tiempos de ejecución que se han cargado.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
|SKU|win:UInt16|1 – CLR de escritorio.<br /><br /> 2 – CoreCLR.|  
|BclVersion – Versión principal|win:UInt16|Versión principal de mscorlib.dll.|  
|BclVersion – Versión secundaria|win:UInt16|Número de versión secundaria de mscorlib.dll.|  
|BclVersion – Número de compilación|win:UInt16|Número de compilación de mscorlib.dll.|  
|BclVersion – QFE|win:UInt16|Número de versión de revisión de mscorlib.dll.|  
|VMVersion – Versión principal|win:UInt16|Versión de clr.dll o coreclr.dll, en función de la SKU.|  
|VMVersion – Versión secundaria|win:UInt16|Versión secundaria de clr.dll o coreclr.dll, en función de la SKU.|  
|VMVersion – Número de compilación|win:UInt16|Número de compilación de clr.dll o coreclr.dll.|  
|VMVersion – QFE|win:UInt16|Número de versión de revisión de clr.dll o coreclr.dll.|  
|StartupFlags|win:UInt32|Marcas de inicio definidas en mscoree.h.|  
|StartupMode|win:UInt8|0x01: ejecutable administrado.<br /><br /> 0x02: CLR hospedado.<br /><br /> 0x04: interoperabilidad administrada de C++.<br /><br /> 0x08: activado para COM.<br /><br /> 0x10: otros.|  
|CommandLine|win:UnicodeString|Distinto de NULL únicamente si StartupMode=0x01.|  
|ComObjectGUID|win:GUID|Distinto de NULL únicamente si StartupMode=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Ruta de acceso al archivo .dll de CLR que se ha cargado en el proceso.|  
  
## <a name="see-also"></a>Consulte también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)
