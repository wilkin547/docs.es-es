---
title: "ICorDebugFunction2::SetJMCStatus (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus (Método)
Marca la función representada por esta instancia de ICorDebugFunction2 para solo mi código ejecución paso a paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bIsJustMyCode`  
 [in] Establecido en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false`.  
  
## <a name="return-values"></a>Valores devueltos  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|La función se ha marcado correctamente.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|La función no se pudieron marcar como código de usuario porque no se pueden depurar.|  
  
## <a name="remarks"></a>Comentarios  
 Un paso a paso desencadene solo mi código omitirá el código de no usuario. Código de usuario debe ser un subconjunto del código depurable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
