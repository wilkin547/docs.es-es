---
description: 'Más información acerca de: ICorDebugExceptionDebugEvent:: GetFlags (método)'
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 54a6c9b0dff2346ca130f80e72fe06dbb3017f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693478"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a>ICorDebugExceptionDebugEvent::GetFlags (método)

Obtiene una marca que indica si se puede interceptar la excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwFlags`  
 enuncia Un puntero a un valor de [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
