---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137240"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)
Quita un punto de interrupción establecido previamente en la dirección especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 de `CORDB_ADDRESS` valor que especifica la dirección en la que se estableció el punto de interrupción.  
  
## <a name="remarks"></a>Comentarios  
 El punto de interrupción especificado se habría establecido previamente mediante una llamada anterior a [ICorDebugProcess2:: SetUnmanagedBreakpoint (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Se puede llamar al método `ClearUnmanagedBreakpoint` mientras se está ejecutando el proceso que se está depurando.  
  
 El método `ClearUnmanagedBreakpoint` devuelve un código de error si el depurador está asociado en modo de solo administración o si no existe ningún punto de interrupción en la dirección especificada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
