---
title: ICorDebugModule::GetFunctionFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acffd24ae9d5aad5f48058eec036f912ee016289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken (Método)
Obtiene la función especificada por el token de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `methodDef`  
 [in] Un `mdMethodDef` símbolo (token) de metadatos que hace referencia a los metadatos de la función.  
  
 `ppFunction`  
 [out] Un puntero a la dirección de un objeto de interfaz de ICorDebugFunction que representa la función.  
  
## <a name="remarks"></a>Comentarios  
 El `GetFunctionFromToken` método devuelve un valor de HRESULT CORDBG_E_FUNCTION_NOT_IL si el valor pasado en `methodDef` no hace referencia a un método de lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
