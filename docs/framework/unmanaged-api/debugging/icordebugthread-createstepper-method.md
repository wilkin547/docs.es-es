---
description: 'Más información acerca de: ICorDebugThread:: Createstepper ((método)'
title: ICorDebugThread::CreateStepper (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: 378ce28281f4f284c36194f993a53598a9de3854
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659366"
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper (Método)

Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo de esta expresión ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppStepper`  
 enuncia Puntero a la dirección de un `ICorDebugStepper` objeto que permite recorrer en iteración el marco activo de este subproceso.  
  
## <a name="remarks"></a>Observaciones  

 El marco activo puede ser código no administrado.  
  
 La `ICorDebugStepper` interfaz se debe utilizar para realizar la ejecución de paso real.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
