---
title: ICorDebugController::Detach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: b98077914d680c908587649fdd517aca9c8dcd40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125437"
---
# <a name="icordebugcontrollerdetach-method"></a>ICorDebugController::Detach (Método)
Desasocia el depurador del dominio del proceso o de la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Comentarios  
 El dominio del proceso o de la aplicación continúa la ejecución con normalidad, pero el objeto "ICorDebugProcess" o "ICorDebugAppDomain" ya no es válido y no se producirán más devoluciones de llamada.  
  
 En la versión .NET Framework 2,0, si está habilitada la depuración no administrada, este método producirá un error debido a las limitaciones del sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
