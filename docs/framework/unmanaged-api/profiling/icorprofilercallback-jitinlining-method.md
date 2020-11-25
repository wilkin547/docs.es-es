---
title: ICorProfilerCallback::JITInlining (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: cf68594620b24f2a5823aa423c5911f2d9d6b328
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725500"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining (Método)

Notifica al generador de perfiles que el compilador Just-in-Time (JIT) está a punto de insertar una función en línea con otra función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parámetros  

 `callerId`  
 de IDENTIFICADOR de la función en la que se `calleeId` insertará la función.  
  
 `calleeId`  
 de IDENTIFICADOR de la función que se va a insertar.  
  
 `pfShouldInline`  
 [out] `true` para permitir que se produzca la inserción; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 El generador de perfiles puede establecer `pfShouldInline` en `false` para evitar que la `calleeId` función se inserte en la `callerId` función. Además, el generador de perfiles puede deshabilitar globalmente la inserción en línea mediante el valor COR_PRF_DISABLE_INLINING de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 Las funciones insertadas en línea no generan eventos para entrar o cerrar. Por lo tanto, el generador de perfiles debe establecer en `pfShouldInline` para `false` generar un gráfico preciso. Si `pfShouldInline` se establece en `false` , afectará al rendimiento, ya que la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
