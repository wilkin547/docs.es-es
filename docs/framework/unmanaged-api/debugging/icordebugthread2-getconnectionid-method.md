---
description: 'Más información sobre: ICorDebugThread2:: Getconnectionid ((método)'
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
ms.openlocfilehash: 0f8035e703d3638b11f4206d9c47e39fe487d71d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658742"
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
 enuncia `CONNID` Que representa el identificador de conexión.  
  
## <a name="remarks"></a>Observaciones  

 El `GetConnectionID` método devuelve cero en el `pdwConnectionId` parámetro, si este subproceso no forma parte de una conexión.  
  
 Si este subproceso está conectado a una instancia de Microsoft SQL Server 2005 Analysis Services (SSAS), se `CONNID` asigna a un identificador de proceso de servidor (SPID).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
