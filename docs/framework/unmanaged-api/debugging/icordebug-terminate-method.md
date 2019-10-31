---
title: ICorDebug::Terminate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134017"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate (Método)
Finaliza el objeto `ICorDebug`.  
  
> [!NOTE]
> no se debe llamar a `Terminate` hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Comentarios  
 se debe llamar a `Terminate` cuando ya no se necesita el objeto `ICorDebug`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
