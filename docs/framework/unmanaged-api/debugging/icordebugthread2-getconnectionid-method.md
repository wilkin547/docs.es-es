---
title: ICorDebugThread2::GetConnectionID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: a81842132769934a6f5f34e6dc462bba77b3854a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138686"
---
# <a name="icordebugthread2getconnectionid-method"></a>ICorDebugThread2::GetConnectionID (Método)
Obtiene el identificador de conexión de este objeto ICorDebugThread2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwConnectionId`  
 enuncia `CONNID` que representa el identificador de conexión.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetConnectionID` devuelve cero en el parámetro `pdwConnectionId`, si este subproceso no forma parte de una conexión.  
  
 Si este subproceso está conectado a una instancia de Microsoft SQL Server 2005 Analysis Services (SSAS), el `CONNID` se asigna a un identificador de proceso de servidor (SPID).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
