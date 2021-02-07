---
description: 'Más información sobre: ICorDebugDataTarget3:: GetLoadedModules (método)'
title: Método de ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: ea6350155fd79b52a37133cad95f624635433a3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764351"
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
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz de ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
