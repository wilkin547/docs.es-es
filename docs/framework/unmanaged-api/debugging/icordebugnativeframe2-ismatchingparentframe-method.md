---
title: ICorDebugNativeFrame2::IsMatchingParentFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: 5bcced647af6436bd8f5b1f3779d9368b6173d11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213041"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>ICorDebugNativeFrame2::IsMatchingParentFrame (Método)
Determina si el marco especificado es el elemento primario del marco actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pPotentialParentFrame`  
 de Puntero al objeto de marco que se desea evaluar para el estado primario.  
  
 `pIsParent`  
 [out] `true` `pPotentialParentFrame`es si es el elemento primario del marco actual; en caso contrario, es `false` .  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El estado primario se devolvió correctamente.|  
|E_FAIL|No se pudo devolver el estado primario.|  
|E_INVALIDARG|`pPotentialParentFrame` o `pIsParent` es null.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Observaciones  
 `IsMatchingParentFrame`Devuelve `true` si el objeto de marco que se pasa al método es el elemento primario del objeto de marco en el que se llamó al método. Si llama al método en un marco que no es un elemento secundario del marco especificado, devuelve un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugNativeFrame2 (Interfaz)](icordebugnativeframe2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
