---
title: CALL_ID (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44db9021a7dbf5b497db3536eddcea020e71bf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="callid-structure"></a>CALL_ID (Estructura)
Proporciona información a un depurador sobre una función que se está llamando. Consulte la [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaz para obtener más información.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`szMachine`|Identifica el equipo que realiza la llamada.|  
|`dwPid`|Identifica el procesador del equipo.|  
|`pUserThread`|Identifica el subproceso que se está ejecutando la llamada.|  
|`addrStackPointer`|Especifica la dirección de la pila de llamadas.|  
|`szEntryPoint`|Especifica la dirección de la llamada.|  
|`szDestinationMachine`|Identifica el equipo que va a ejecutar la llamada.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vea también  
 [INotifySink2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
