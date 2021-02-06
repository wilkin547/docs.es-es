---
description: 'Más información sobre: ICorProfilerInfo3:: GetAppDomainsContainingModule ((método)'
title: ICorProfilerInfo3::GetAppDomainsContainingModule (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 0f0fea5b01b80b110d7ab041574dc195162cb508
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646847"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a>ICorProfilerInfo3::GetAppDomainsContainingModule (Método)

Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 [in] Identificador del módulo cargado.  
  
 `cAppDomainIds`  
 [in] Tamaño de la matriz `appDomainIds`.  
  
 `pcAppDomainIds`  
 [out] Puntero al número total de elementos devueltos.  
  
 `appDomainIds`  
 [out] Matriz de valores de identificador de dominio de aplicación.  
  
## <a name="remarks"></a>Observaciones  

 El método usa búferes asignados al llamador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionEnum (Interfaz)](icorprofilerfunctionenum-interface.md)
- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
