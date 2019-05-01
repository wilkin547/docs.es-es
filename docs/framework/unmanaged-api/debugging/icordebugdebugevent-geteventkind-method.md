---
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62eede48eea01563dbc3e170720694a24343d0a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964767"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>Método ICorDebugDebugEvent::GetEventKind
Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 pDebugEventKind  
 Un puntero a un [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) miembro de enumeración que indica el tipo de evento.  
  
## <a name="remarks"></a>Comentarios  
 Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
