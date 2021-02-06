---
description: 'Más información acerca de: ICorDebugThread:: Getregisterset ((método)'
title: ICorDebugThread::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: f61ccb34eabc1f4d8b8db8a0b78e3ddde9aa136d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658911"
---
# <a name="icordebugthreadgetregisterset-method"></a>ICorDebugThread::GetRegisterSet (Método)

Obtiene un puntero de interfaz al conjunto de registros asociado a la parte activa de este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppRegisters`  
 enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface que representa el conjunto de registros para la parte activa de este subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
