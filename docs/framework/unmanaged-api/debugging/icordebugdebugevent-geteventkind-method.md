---
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713683"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>Método ICorDebugDebugEvent::GetEventKind

Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 pDebugEventKind  
 Un puntero a un miembro de la enumeración [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) que indica el tipo de evento.  
  
## <a name="remarks"></a>Comentarios  

 Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
