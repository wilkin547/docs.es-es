---
description: 'Más información sobre: ICorDebugThread2:: Getvolatileosthreadid ((método)'
title: ICorDebugThread2::GetVolatileOSThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
ms.openlocfilehash: 2c198577195c9b1e4a3a74fae686e405b22120eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658599"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a>ICorDebugThread2::GetVolatileOSThreadID (Método)

Obtiene el identificador del subproceso del sistema operativo para este ICorDebugThread2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwTid`  
 enuncia Identificador del subproceso del sistema operativo para este subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
