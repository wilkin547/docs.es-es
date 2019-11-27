---
title: ICorProfilerCallback::AppDomainShutdownFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445198"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>ICorProfilerCallback::AppDomainShutdownFinished (Método)
Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `appDomainId`  
 de Identifica el dominio en el que se almacenan los ensamblados de la aplicación.  
  
 `hrStatus`  
 de Un valor HRESULT que indica si el dominio de aplicación se ha descargado correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `appDomainId` no es válido para una solicitud de información después de que se devuelva el método [ICorProfilerCallback:: appdomainshutdownstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) .  
  
 Algunas partes de la descarga del dominio de aplicación pueden continuar después de la devolución de llamada de `AppDomainCreationFinished`. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la descarga del dominio de aplicación se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
