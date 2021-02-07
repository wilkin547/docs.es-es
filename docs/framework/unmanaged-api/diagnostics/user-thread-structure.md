---
description: 'Más información acerca de: estructura de USER_THREAD'
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
ms.openlocfilehash: a4bd22073b7610307e67107781bdb68a15ef795f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761273"
---
# <a name="user_thread-structure"></a>USER_THREAD (Estructura)

Proporciona información a un depurador sobre un subproceso. Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pSidBuffer`|Dirección del búfer de subproceso.|  
|`dwSidLen`|Longitud del búfer de subprocesos, en bytes.|  
|`dwTid`|IDENTIFICADOR de subproceso.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vea también

- [Método SetNotifyFilter](inotifysource2-setnotifyfilter-method.md)
- [Estructuras de almacén de símbolos de diagnósticos](diagnostics-symbol-store-structures.md)
