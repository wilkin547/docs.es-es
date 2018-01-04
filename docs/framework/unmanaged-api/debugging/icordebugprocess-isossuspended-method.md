---
title: "ICorDebugProcess::IsOSSuspended (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsOSSuspended
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended (Método)
Obtiene un valor que indica si el subproceso especificado se ha suspendido porque el depurador detener este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `threadID`  
 [in] El identificador del subproceso en cuestión.  
  
 `pbSuspended`  
 [out] Un puntero a un valor booleano que es `true` si el subproceso especificado se ha suspendido; de lo contrario *`pbSuspended` es `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el subproceso especificado se ha suspendido porque el depurador detener este proceso, el recuento de suspensiones de Win32 del subproceso especificado se incrementa en uno. La interfaz de usuario (UI) del depurador puede tener en cuenta esta información si muestra el sistema operativo (SO) suspende el recuento del subproceso para el usuario.  
  
 El `IsOSSuspended` método tiene sentido sólo en el contexto de depuración no administrada. Durante la depuración administrada, los subprocesos se forma cooperativa suspendido en lugar de suspendido por el sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
