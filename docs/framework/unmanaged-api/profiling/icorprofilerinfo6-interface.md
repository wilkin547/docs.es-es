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
ms.openlocfilehash: fba57a88cd3af582b4edf0e5bdbf6ac48020c9f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495520"
---
# <a name="icorprofilerinfo6-interface"></a>Interfaz ICorProfilerInfo6
[Se admite en el .NET Framework 4,6 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo5](icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un módulo Ngen determinado e insertan un método determinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces para generación de perfiles](profiling-interfaces.md)
