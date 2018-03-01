---
title: "ICorProfilerInfo2::GetRVAStaticAddress (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4320ed3cdd3d17932d03e98d4d35d27adad2532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress (Método)
Obtiene la dirección del campo estático de dirección virtual relativa (RVA) especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de la clase que contiene el campo estático de RVA solicitado.  
  
 `fieldToken`  
 [in] Símbolo (token) de metadatos para el campo estático de RVA solicitado.  
  
 `ppAddress`  
 [out] Un puntero a la dirección del campo estático de RVA.  
  
## <a name="remarks"></a>Comentarios  
 El `GetRVAStaticAddress` método puede devolver uno de los siguientes:  
  
-   Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.  
  
-   Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados. Estas direcciones pueden no ser válidas después de recolección de elementos no utilizados, por lo que después de recolección de elementos no utilizados, los generadores de perfiles no deben suponer que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetRVAStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y pueden ser la raíz los objetos de colección de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
