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
ms.openlocfilehash: a7f62385031967c164915fd31735a6d962f557fa
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894987"
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
 El `GetName` método devuelve un HRESULT S_OK si el nombre de archivo del módulo coincide con el nombre en el disco. `GetName`Devuelve un valor de HRESULT S_FALSE si se ha fabricado el nombre, por ejemplo para un módulo dinámico o en memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
