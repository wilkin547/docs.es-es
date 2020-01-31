---
title: ICorProfilerThreadEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: b9fb308f19ff09218c97b030296b9a3d4f0f2512
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868192"
---
# <a name="icorprofilerthreadenum-interface"></a>ICorProfilerThreadEnum (Interfaz)
Proporciona métodos para iterar secuencialmente por una colección de subprocesos en Common Language Runtime.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](icorprofilerthreadenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerThreadEnum`.|  
|[GetCount (método)](icorprofilerthreadenum-getcount-method.md)|Obtiene el número de subprocesos utilizados por la aplicación.|  
|[Next (método)](icorprofilerthreadenum-next-method.md)|Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.|  
|[Reset (método)](icorprofilerthreadenum-reset-method.md)|Mueve el cursor del enumerador a la posición inicial de la secuencia.|  
|[Skip (método)](icorprofilerthreadenum-skip-method.md)|Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.|  
  
## <a name="remarks"></a>Notas  
 La interfaz `ICorProfilerThreadEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
