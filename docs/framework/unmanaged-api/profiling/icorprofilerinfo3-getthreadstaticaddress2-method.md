---
title: "ICorProfilerInfo3::GetThreadStaticAddress2 (Método)"
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
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 136b68f886899430dbfc672b8e3e534d093bc617
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>ICorProfilerInfo3::GetThreadStaticAddress2 (Método)
Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de la clase que contiene el campo estático de subproceso solicitado.  
  
 `fieldToken`  
 [in] El token de metadatos para el campo estático de subproceso solicitado.  
  
 `appDomainId`  
 [in] Identificador de dominio de la aplicación.  
  
 `threadId`  
 [in] El identificador del subproceso que constituye el ámbito del campo estático solicitado.  
  
 `ppAddress`  
 [out] Un puntero a la dirección del campo estático que está dentro del subproceso especificado.  
  
## <a name="remarks"></a>Comentarios  
 El `GetThreadStaticAddress2` método puede devolver uno de los siguientes:  
  
-   Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.  
  
-   Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados. Estas direcciones pueden no ser válidas después de recolección de elementos no utilizados, por lo que después de recolección de elementos no utilizados, los generadores de perfiles no deben suponer que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress2` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y objetos de la colección de elementos no utilizados de la raíz.  
  
 El [ICorProfilerInfo2:: GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) método es similar a la `GetThreadStaticAddress2` método, pero no acepta un argumento de dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
