---
title: Interfaz ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: 80ac17a96e5c1c8c32cfc336da6c2be30eaf80fd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868374"
---
# <a name="icorprofilerinfo6-interface"></a>Interfaz ICorProfilerInfo6
[Se admite en el .NET Framework 4,6 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo5](icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un módulo Ngen determinado e insertan un método determinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
