---
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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867030"
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
  
## <a name="members"></a>Miembros  
  
|Miembros|Descripción|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Indica que se deben pasar valores para todos los parámetros de `StackSnapshotCallback`, excepto el parámetro `context`.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Indica que se deben pasar valores para todos los parámetros de `StackSnapshotCallback`, incluido el parámetro `context`.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Indica que se usará un algoritmo de recorrido de pila alternativo más sencillo.|  
  
## <a name="remarks"></a>Notas  
 Los valores que proporciona la enumeración `COR_PRF_SNAPSHOT_INFO` se pasan como parámetros al método [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [DoStackSnapshot (método)](icorprofilerinfo2-dostacksnapshot-method.md)
- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
