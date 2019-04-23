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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c8dd8795fc3699176490ea0bb9b2e999038afb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124883"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate (Método)
Finaliza el proceso con el código de salida especificado.  
  
> [!NOTE]
>  Este método es un contenedor para Win32 `TerminateProcess` función. Por lo tanto, `Terminate` usa el código de salida en la misma forma en que Win32 `TerminateProcess` lo usa la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `exitCode`  
 [in] Un valor numérico que es el código de salida. Los valores numéricos válidos se definen en Winbase.h.  
  
## <a name="remarks"></a>Comentarios  
 Si el proceso se detiene cuando `Terminate` es llama, el proceso debe continuar utilizando el [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método para que el depurador recibe confirmación de la finalización mediante el [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) o [ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) devolución de llamada.  
  
> [!NOTE]
>  Este método no está implementado por un dominio de aplicación. Es decir, no se implementa en el <xref:System.AppDomain> nivel.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
