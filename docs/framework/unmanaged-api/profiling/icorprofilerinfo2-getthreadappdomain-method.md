---
description: 'Más información acerca de: ICorProfilerInfo2:: GetThreadAppDomain ((método)'
title: ICorProfilerInfo2::GetThreadAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: b480388254a6ee84db9f6c3e8d44b7358246502a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647068"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a>ICorProfilerInfo2::GetThreadAppDomain (Método)

Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando código actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadId`  
 de IDENTIFICADOR que especifica el subproceso.  
  
 `pAppDomainId`  
 enuncia Puntero al identificador del dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
