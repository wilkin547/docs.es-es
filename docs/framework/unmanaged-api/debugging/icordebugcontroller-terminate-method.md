---
title: "ICorDebugController::Terminate (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e7647df7a67d8357e72f8f41b0b3f586675aaac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate (Método)
Finaliza el proceso con el código de salida especificado.  
  
> [!NOTE]
>  Este método es un contenedor de Win32 `TerminateProcess` función. Por lo tanto, `Terminate` utiliza el código de salida de la misma forma en que Win32 `TerminateProcess` función lo usa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `exitCode`  
 [in] Un valor numérico que es el código de salida. Los valores numéricos válidos se definen en Winbase.h.  
  
## <a name="remarks"></a>Comentarios  
 Si el proceso se detiene cuando `Terminate` es llama, el proceso debe continuar usando el [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método para que el depurador reciba confirmación de la finalización a través de la [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) devolución de llamada.  
  
> [!NOTE]
>  Este método no se implementa en un dominio de aplicación. Es decir, no se implementa en el <xref:System.AppDomain> nivel.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
