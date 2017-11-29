---
title: "ICorProfilerCallback::JITInlining (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining (Método)
Notifica al generador de perfiles que el compilador just-in-time (JIT) está a punto de insertar una función en línea con otra función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `callerId`  
 [in] El identificador de la función en la que el `calleeId` función que se van a insertar.  
  
 `calleeId`  
 [in] Id. de la función que se va a insertar.  
  
 `pfShouldInline`  
 [out] `true` para permitir la inserción; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Puede establecer el generador de perfiles `pfShouldInline` a `false` para evitar la `calleeId` función de que se va a insertar en el `callerId` (función). Además, el generador de perfiles puede deshabilitar globalmente inserción en línea mediante el uso del valor COR_PRF_DISABLE_INLINING de la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.  
  
 Las funciones insertadas inline no provocan eventos de entrada o salida. Por lo tanto, debe establecer el generador de perfiles `pfShouldInline` a `false` para generar un gráfico de llamadas preciso. Establecer `pfShouldInline` a `false` afectará al rendimiento, porque la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
