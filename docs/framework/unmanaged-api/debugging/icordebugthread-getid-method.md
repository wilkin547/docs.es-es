---
description: 'Más información acerca de: ICorDebugThread:: GetID (método)'
title: ICorDebugThread::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d089201527da67299b64cdf074bdd331f22375a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659093"
---
# <a name="icordebugthreadgetid-method"></a>ICorDebugThread::GetID (Método)

Obtiene el identificador del sistema operativo actual de la parte activa de esta ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwThreadId`  
 enuncia Identificador del subproceso.  
  
## <a name="remarks"></a>Observaciones  

 El identificador del sistema operativo puede cambiar durante la ejecución de un proceso y puede ser un valor diferente para distintas partes del subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
