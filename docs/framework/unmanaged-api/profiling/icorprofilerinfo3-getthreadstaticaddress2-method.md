---
title: ICorProfilerInfo3::GetThreadStaticAddress2 (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49139f5b1f65bc2e258362d9b47f4e0d44cc6894
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481526"
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
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de la clase que contiene el campo de subproceso estático solicitado.  
  
 `fieldToken`  
 [in] El token de metadatos para el campo de subproceso estático solicitado.  
  
 `appDomainId`  
 [in] Identificador de dominio de la aplicación.  
  
 `threadId`  
 [in] El identificador del subproceso que es el ámbito para el campo estático solicitado.  
  
 `ppAddress`  
 [out] Un puntero a la dirección del campo estático que se encuentra dentro del subproceso especificado.  
  
## <a name="remarks"></a>Comentarios  
 El `GetThreadStaticAddress2` método puede devolver uno de los siguientes:  
  
-   Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.  
  
-   Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados. Estas direcciones pueden no ser válidas después de la recolección de elementos, por lo que después de la recolección de elementos, los generadores de perfiles no deben suponer que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress2` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque ya se pueden inicializar algunos de los campos estáticos y los objetos de colección de elementos no utilizados de la raíz.  
  
 El [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) método es similar a la `GetThreadStaticAddress2` método, pero no acepta un argumento de dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
