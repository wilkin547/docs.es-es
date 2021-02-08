---
description: 'Más información acerca de: ICorDebugManagedCallback:: ExitProcess (método)'
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
ms.openlocfilehash: 3418931b8397edefcb801986275c35b28e00072d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790963"
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
  
## <a name="remarks"></a>Observaciones  

 No se puede continuar a partir de un `ExitProcess` evento. Este evento puede desencadenarse de forma asincrónica en otros eventos mientras el proceso parece estar detenido. Esto puede ocurrir si el proceso finaliza mientras se detiene, normalmente debido a una fuerza externa.  
  
 Si el Common Language Runtime (CLR) ya está enviando una devolución de llamada administrada, este evento se retrasará hasta que se devuelva esa devolución de llamada.  
  
 El `ExitProcess` evento es el único evento de salida o descarga que se garantiza que se llamará al apagar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
