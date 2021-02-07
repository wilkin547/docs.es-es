---
description: 'Más información sobre: ICorDebugAppDomain4:: GetObjectForCCW (método)'
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 5ba4923c933d02f5d6ad5c1fd8c4d0e2ddb410d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754139"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Método de ICorDebugAppDomain4::GetObjectForCCW

Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ccwPointer`  
 [in] Puntero de contenedor CCW (COM callable wrapper).  
  
 `ppManagedObject`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz de ICorDebugAppDomain4](icordebugappdomain4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
