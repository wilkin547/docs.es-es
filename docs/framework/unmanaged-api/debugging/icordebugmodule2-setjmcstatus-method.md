---
title: ICorDebugModule2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a56b5c31c26dbe5c5371fdb7a10c13ad11847117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus (Método)
Establece el estado de "sólo mi código" (JMC) de todos los métodos de todas las clases en este ICorDebugModule2 en el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bIsJustMycode`  
 [in] Establecido en `true` si el código depurado; en caso contrario, se establece en `false`.  
  
 `cTokens`  
 [in] Tamaño de la matriz `pTokens`.  
  
 `pTokens`  
 [in] Una matriz de `mdToken` valores, cada uno de los cuales se refiere a un método que tendrá su estado JMC establecido en!`bIsJustMycode`.  
  
## <a name="remarks"></a>Comentarios  
 El estado JMC de cada método que se especifica en el `pTokens` matriz se establece con el valor opuesto de la `bIsJustMycode` valor. El estado de todos los demás métodos de este módulo se establece en el `bIsJustMycode` valor.  
  
 El `SetJMCStatus` método borra toda la configuración JMC anterior de este módulo.  
  
 El `SetJMCStatus` método devuelve un HRESULT de S_OK si todas las funciones se establecieron correctamente. Devuelve un HRESULT de CORDBG_E_FUNCTION_NOT_DEBUGGABLE si algunas funciones que se marcan `true` no son depurable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
