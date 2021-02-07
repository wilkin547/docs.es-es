---
description: 'Más información acerca de: ICorDebugProcess:: ClearCurrentException ((método)'
title: ICorDebugProcess::ClearCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 6f356078d8d303acb39cbaa500b7592185ad55ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754048"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException (Método)

Borra la excepción no administrada actual en el subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadID`  
 de IDENTIFICADOR del subproceso en el que se borrará la excepción no administrada actual.  
  
## <a name="remarks"></a>Observaciones  

 Llame a este método antes de llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) cuando un subproceso haya comunicado una excepción no administrada que el código depurado debe omitir. Esto borrará los eventos en banda (IB) y fuera de banda (OOB) pendientes en el subproceso determinado. Todos los puntos de interrupción de OOB y las excepciones de un solo paso se borran automáticamente.  
  
 Use [ICorDebugThread2:: interceptcurrentexception (](icordebugthread2-interceptcurrentexception-method.md) para interceptar la excepción administrada actual en un subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
