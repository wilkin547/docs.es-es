---
title: ICorDebugModule::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39467c067e50f2d553b35a41b0f783e0fc82156
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988036"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName (Método)
Obtiene el nombre de archivo del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cchname`  
 [in] Tamaño de la matriz `szName`.  
  
 `pcchName`  
 [in] Un puntero a la longitud del nombre devuelto.  
  
 `szName`  
 [out] Una matriz que almacena el nombre devuelto.  
  
## <a name="remarks"></a>Comentarios  
 El `GetName` método devuelve S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco. `GetName` Devuelve un HRESULT S_FALSE si el nombre es fabricadas, por ejemplo, para un módulo dinámico o en memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
