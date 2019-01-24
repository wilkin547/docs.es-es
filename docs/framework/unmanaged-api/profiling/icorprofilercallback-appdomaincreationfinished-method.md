---
title: ICorProfilerCallback::AppDomainCreationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48d43d9107d010b12167b977acd2e500437c039f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501719"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished (Método)
Notifica al generador de perfiles que se ha creado un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `appDomainId`  
 [in] Identifica el dominio que se ha creado.  
  
 `hrStatus`  
 [in] Un HRESULT que indica si se completó correctamente la creación del dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 El identificador de aplicación no es válido para cualquier solicitud de información hasta que el `AppDomainCreationFinished` se llama al método.  
  
 Algunas partes de la carga del dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada. Un error HRESULT en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
