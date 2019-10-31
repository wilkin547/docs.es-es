---
title: ICorDebugController::Terminate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125336"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate (Método)
Finaliza el proceso con el código de salida especificado.  
  
> [!NOTE]
> Este método es un contenedor para la función `TerminateProcess` de Win32. Por lo tanto, `Terminate` utiliza el código de salida de la misma forma que la función `TerminateProcess` de Win32 la usa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `exitCode`  
 de Un valor numérico que es el código de salida. Los valores numéricos válidos se definen en Winbase. h.  
  
## <a name="remarks"></a>Comentarios  
 Si el proceso se detiene cuando se llama a `Terminate`, el proceso debe continuar usando el método [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para que el depurador reciba la confirmación de la terminación a través de [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)La devolución de llamada ExitProcess o [ICorDebugManagedCallback:: exitappdomain (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Este método no está implementado por un dominio de aplicación. Es decir, no se implementa en el nivel de <xref:System.AppDomain>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
