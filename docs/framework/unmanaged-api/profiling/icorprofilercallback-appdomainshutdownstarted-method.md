---
title: ICorProfilerCallback::AppDomainShutdownStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9d1cf182eaf6f245baa5d898bac3ca7d3190234
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763093"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a>ICorProfilerCallback::AppDomainShutdownStarted (Método)
Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `appDomainId`  
 [in] Identifica el dominio en el que se almacenan los ensamblados de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `appDomainId` no es válido para cualquier solicitud de información después de la `AppDomainShutdownStarted` devuelve del método, se trata de la última oportunidad para obtener información acerca de este dominio de aplicación del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
