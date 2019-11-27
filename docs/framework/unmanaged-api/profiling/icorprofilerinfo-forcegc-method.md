---
title: ICorProfilerInfo::ForceGC (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 9f97da4e68d4b76178198e91c3fb8f08b56dda7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448190"
---
# <a name="icorprofilerinfoforcegc-method"></a>ICorProfilerInfo::ForceGC (Método)
Fuerza la recolección de elementos no utilizados en el Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Comentarios  
 Solo se debe llamar al método `ForceGC` desde un subproceso que nunca ha ejecutado código administrado y no tiene ninguna devolución de llamada del generador de perfiles en su pila. La implementación más cómoda es crear un subproceso independiente en el generador de perfiles que llama a `ForceGC` cuando se señala.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
