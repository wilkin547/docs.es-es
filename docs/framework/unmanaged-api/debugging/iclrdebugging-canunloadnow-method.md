---
title: ICLRDebugging::CanUnloadNow (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: e89d936c528ea7482487a8629dbd882f6f67483e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723576"
---
# <a name="iclrdebuggingcanunloadnow-method"></a>ICLRDebugging::CanUnloadNow (Método)

Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hmodule`  
 de La dirección base de un módulo en el proceso de destino.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se puede descargar el módulo al que hace referencia `hmodule` .|  
|S_FALSE|El módulo al que hace referencia `hmodule` está todavía en uso.|  
|COR_E_NOT_CLR|El módulo indicado no es un módulo CLR.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  

 Este método comprueba si se han liberado todas las instancias de las `ICorDebug*` interfaces y ningún subproceso está actualmente dentro de una llamada al método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
