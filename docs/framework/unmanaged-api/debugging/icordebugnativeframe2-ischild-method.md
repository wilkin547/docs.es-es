---
title: ICorDebugNativeFrame2::IsChild (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 759ba7bd46f8231143e743aa5ffcabffeb99c3b6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205111"
---
# <a name="icordebugnativeframe2ischild-method"></a>ICorDebugNativeFrame2::IsChild (Método)
Determina si el marco actual es un marco secundario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pIsChild`  
 enuncia Valor booleano que especifica si el marco actual es un marco secundario.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El estado secundario se devolvió correctamente.|  
|E_FAIL|No se pudo devolver el estado secundario.|  
|E_INVALIDARG|`pIsChild` es null.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Observaciones  
 El `IsChild` método devuelve `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco. Si este es el caso, use el método [ismatchingparentframe (](icordebugnativeframe2-ismatchingparentframe-method.md) para comprobar si un marco es su elemento primario.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugNativeFrame2 (Interfaz)](icordebugnativeframe2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
