---
title: Método de ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: efbada02b7a24e0a7ed613b86b8a4a1a0b5b051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713758"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>Método de ICorDebugDataTarget3::GetLoadedModules

Obtiene una lista de los módulos que se han cargado hasta ahora.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cRequestedModules`  
 [in] Número de módulos para los que se solicita información.  
  
 `pcFetchedModules`  
 [out] Puntero al número de módulos sobre qué información se devolvió.  
  
 `pLoadedModules`  
 enuncia Puntero a una matriz de objetos [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) que proporcionan información sobre los módulos cargados.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz de ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
