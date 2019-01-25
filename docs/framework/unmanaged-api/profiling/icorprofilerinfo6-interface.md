---
title: ICorProfilerInfo6 (interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53120508c4810270747f749f1adfbae6ba800404
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567898"
---
# <a name="icorprofilerinfo6-interface"></a>ICorProfilerInfo6 (interfaz)
[Compatible con .NET Framework 4.6 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un determinado módulo NGen y en línea un método determinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que se alinean en el cuerpo de un método determinado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
