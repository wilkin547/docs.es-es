---
description: 'Más información sobre: ICorDebugLoadedModule:: GetBaseAddress ((método)'
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 2852131d543cfb9593cf4ff607d1f752226c2880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801272"
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
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz de ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
