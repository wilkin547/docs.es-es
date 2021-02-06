---
description: 'Más información sobre: ICorProfilerCallback:: AppDomainShutdownFinished ((método)'
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
ms.openlocfilehash: e08a4f7e03bfd18d9c6a2fdf56bfab8c68f9c379
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648261"
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

- `appDomainId`

  \[en] identifica el dominio en el que se almacenan los ensamblados de la aplicación.

- `hrStatus`

  \[in] un valor HRESULT que indica si el dominio de aplicación se ha descargado correctamente.

## <a name="remarks"></a>Observaciones  

 El valor de `appDomainId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: appdomainshutdownstarted (](icorprofilercallback-appdomainshutdownstarted-method.md) devuelva.  
  
 Algunas partes de la descarga del dominio de aplicación pueden continuar después de la `AppDomainCreationFinished` devolución de llamada. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del dominio de aplicación se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
