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
ms.openlocfilehash: 41b2e009f8f017a72147232015ea2357ae922ca1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793649"
---
# <a name="iclrdebuggingcanunloadnow-method"></a>ICLRDebugging::CanUnloadNow (Método)
Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a>Parameters  
 `hmodule`  
 de La dirección base de un módulo en el proceso de destino.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se puede descargar el módulo al que hace referencia `hmodule`.|  
|S_FALSE|El módulo al que hace referencia `hmodule` todavía está en uso.|  
|COR_E_NOT_CLR|El módulo indicado no es un módulo CLR.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  
 Este método comprueba si se han liberado todas las instancias de las interfaces de `ICorDebug*` y ningún subproceso está actualmente dentro de una llamada al método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
