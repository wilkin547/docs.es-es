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
ms.openlocfilehash: b27e7a2cdcbfc3a88a734230118d99c2dd5c700e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129537"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName (Método)
Obtiene el nombre de archivo del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
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
 de Puntero a la longitud del nombre devuelto.  
  
 `szName`  
 enuncia Matriz que almacena el nombre devuelto.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetName` devuelve un HRESULT S_OK si el nombre de archivo del módulo coincide con el nombre en el disco. `GetName` devuelve un valor de HRESULT S_FALSE si se ha fabricado el nombre, por ejemplo para un módulo dinámico o en memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
