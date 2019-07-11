---
title: ICorProfilerInfo2::GetAppDomainStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e68178a71d7ba73b4956a7d23854c23300301d8e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747856"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress (Método)
Obtiene la dirección del campo estático del dominio de aplicación especificada que está en el ámbito del dominio de aplicación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de clase de la clase que contiene el campo estático de dominio de aplicación solicitada.  
  
 `fieldToken`  
 [in] El token de metadatos para el campo estático de dominio de aplicación solicitada.  
  
 `appDomainId`  
 [in] El Id. del dominio de aplicación que es el ámbito para el campo estático solicitado.  
  
 `ppAddress`  
 [out] Un puntero a la dirección del campo estático que se encuentra dentro del dominio de aplicación especificado.  
  
## <a name="remarks"></a>Comentarios  
 El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:  
  
- Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.  
  
- Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados. Estas direcciones pueden no ser válidas después de la recolección de elementos, por lo que después de la recolección de elementos, los generadores de perfiles no deben suponer que son válidos.  
  
 Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque ya se pueden inicializar algunos de los campos estáticos y los objetos de colección de elementos no utilizados de la raíz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
