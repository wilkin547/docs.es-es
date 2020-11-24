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
ms.openlocfilehash: 460aeeca9d62ce91a11a24d774c8e681ed4f00ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679811"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate (Método)

Finaliza el proceso con el código de salida especificado.  
  
> [!NOTE]
> Este método es un contenedor para la función de Win32 `TerminateProcess` . Por lo tanto, `Terminate` utiliza el código de salida del mismo modo que la función de Win32 `TerminateProcess` lo utiliza.  
  
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

 Si el proceso se detiene cuando `Terminate` se llama a, el proceso debe continuar usando el método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para que el depurador reciba la confirmación de la finalización a través de la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: exitappdomain (](icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Este método no está implementado por un dominio de aplicación. Es decir, no se implementa en el <xref:System.AppDomain> nivel.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
