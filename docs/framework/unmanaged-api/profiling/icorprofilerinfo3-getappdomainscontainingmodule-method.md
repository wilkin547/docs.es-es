---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343834492776fdb09a68210fb80138ec2c588773
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741157"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a>ICorProfilerInfo3::GetAppDomainsContainingModule (Método)
Obtiene los identificadores de los dominios de aplicación en los que se cargó el módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] Identificador del módulo cargado.  
  
 `cAppDomainIds`  
 [in] Tamaño de la matriz `appDomainIds`.  
  
 `pcAppDomainIds`  
 [out] Puntero al número total de elementos devueltos.  
  
 `appDomainIds`  
 [out] Matriz de valores de identificador de dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 El método usa búferes asignados al llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerFunctionEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
