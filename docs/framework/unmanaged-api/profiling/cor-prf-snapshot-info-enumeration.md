---
description: 'Más información acerca de: enumeración COR_PRF_SNAPSHOT_INFO'
title: COR_PRF_SNAPSHOT_INFO (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: fcdaeeb6170cb9998281100c5628b3d95f9e9326
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753346"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>COR_PRF_SNAPSHOT_INFO (Enumeración)

Especifica la cantidad de datos que se van a devolver con una instantánea de pila en cada llamada a la función [StackSnapshotCallback](stacksnapshotcallback-function.md) del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Members  
  
|Members|Descripción|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, excepto el `context` parámetro.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, incluido el `context` parámetro.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Indica que se usará un algoritmo de recorrido de pila alternativo más sencillo.|  
  
## <a name="remarks"></a>Observaciones  

 Los valores que proporciona la `COR_PRF_SNAPSHOT_INFO` enumeración se pasan como parámetros al método [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
