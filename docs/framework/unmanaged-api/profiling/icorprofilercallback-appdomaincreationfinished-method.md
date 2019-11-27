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
ms.openlocfilehash: eaf0ae2a1b86234495c1804cff8b74331b3e8021
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445273"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished (Método)
Notifica al generador de perfiles que se ha creado un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a>Parámetros  
 `appDomainId`  
 de Identifica el dominio que se ha creado.  
  
 `hrStatus`  
 de HRESULT que indica si la creación del dominio de aplicación se completó correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El ID. de aplicación no es válido para ninguna solicitud de información hasta que se llama al método `AppDomainCreationFinished`.  
  
 Algunas partes de la carga del dominio de aplicación pueden continuar después de la devolución de llamada de `AppDomainCreationFinished`. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
