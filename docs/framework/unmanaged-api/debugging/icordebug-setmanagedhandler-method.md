---
description: 'Más información acerca de: ICorDebug:: SetManagedHandler ((método)'
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
ms.openlocfilehash: 5817bd39a2c4e7c71dc12ca8d2d9b1263d116ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754360"
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

 `SetManagedHandler` se debe llamar al método en el momento de la creación.  
  
 Si la `ICorDebugManagedCallback` implementación no contiene interfaces suficientes para controlar los eventos de depuración de la aplicación que se está depurando, `SetManagedHandler` devuelve un valor HRESULT de E_NOINTERFACE.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
