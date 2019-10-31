---
title: ICorDebugManagedCallback::ExitProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130788"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess (Método)
Notifica al depurador que se ha salido de un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 de Un puntero a un objeto ICorDebugProcess que representa el proceso.  
  
## <a name="remarks"></a>Comentarios  
 No se puede continuar desde un evento `ExitProcess`. Este evento puede desencadenarse de forma asincrónica en otros eventos mientras el proceso parece estar detenido. Esto puede ocurrir si el proceso finaliza mientras se detiene, normalmente debido a una fuerza externa.  
  
 Si el Common Language Runtime (CLR) ya está enviando una devolución de llamada administrada, este evento se retrasará hasta que se devuelva esa devolución de llamada.  
  
 El evento `ExitProcess` es el único evento de salida o descarga que se garantiza que se llamará al apagar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
