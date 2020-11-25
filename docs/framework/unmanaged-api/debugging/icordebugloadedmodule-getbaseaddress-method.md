---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 29153da86812583a0ea789da0c0816f08e0a6b43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698083"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a>Método de ICorDebugLoadedModule::GetBaseAddress

Obtiene la dirección base del módulo cargado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAddress`  
 [out] Puntero a la dirección base del módulo cargado.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz de ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
