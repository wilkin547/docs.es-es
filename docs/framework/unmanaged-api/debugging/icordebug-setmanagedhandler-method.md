---
title: ICorDebug::SetManagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: a197d260c55d24f906da7d7f2768bb7ba1ad751f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895348"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler (Método)
Especifica el objeto de controlador de eventos para los eventos administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCallback`  
 de Un puntero a un objeto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , que es el objeto del controlador de eventos.  
  
## <a name="remarks"></a>Observaciones  
 `SetManagedHandler`se debe llamar al método en el momento de la creación.  
  
 Si la `ICorDebugManagedCallback` implementación no contiene interfaces suficientes para controlar los eventos de depuración de la aplicación que se está depurando, `SetManagedHandler` devuelve un valor HRESULT de E_NOINTERFACE.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICorDebug (Interfaz)](icordebug-interface.md)
