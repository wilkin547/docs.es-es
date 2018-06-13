---
title: USER_THREAD (Estructura)
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93e96d6f8570e6aef7bfc18ef2859dc1e86ec8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429036"
---
# <a name="userthread-structure"></a>USER_THREAD (Estructura)
Proporciona información a un depurador sobre un subproceso. Para obtener más información, consulte el [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pSidBuffer`|Dirección del búfer de subprocesos.|  
|`dwSidLen`|Longitud del búfer de subprocesos, en bytes.|  
|`dwTid`|Identificador de subproceso.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vea también  
 [SetNotifyFilter (método)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
