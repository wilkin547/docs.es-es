---
title: ICorProfilerAssemblyReferenceProvider (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65c18f534771407b2dcf4710e2604e0b30cbdcdb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611051"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>ICorProfilerAssemblyReferenceProvider (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Permite al generador de perfiles informar a common language runtime (CLR) de las referencias de ensamblado que el generador de perfiles agregará en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Informa a CLR de una referencia de ensamblado que el generador de perfiles planea agregar en el [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR pasa el generador de perfiles una `ICorProfilerAssemblyReferenceProvider` objeto de interfaz en el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada. Esto permite al generador de perfiles informar a CLR de referencias de ensamblado que el generador de perfiles planea agregar más adelante en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md). . Mejora la precisión del rastreador de cierres de referencia de ensamblado de CLR y de sus algoritmos para determinar si los ensamblados se pueden compartir.  
  
 Esta interfaz se puede usar solo en el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada que se pasa este objeto de interfaz al generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
