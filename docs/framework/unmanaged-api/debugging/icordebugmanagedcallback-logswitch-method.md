---
title: ICorDebugManagedCallback::LogSwitch (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: db6ccd63bbeadd7dcff1c7f8491b59017d431d12
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720703"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch (Método)

Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un modificador de depuración o traza.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parámetros  

 `PAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que creó, modificó o eliminó un modificador de depuración/seguimiento.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.  
  
 `lLevel`  
 de Valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.  
  
 `ulReason`  
 de Un valor de la enumeración [logswitchcallreason (](logswitchcallreason-enumeration.md) que indica la operación realizada en el modificador de depuración/seguimiento.  
  
 `pLogSwitchName`  
 de Puntero al nombre del modificador de depuración/seguimiento.  
  
 `pParentName`  
 de Puntero al nombre del elemento primario del modificador de depuración/seguimiento.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
