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
ms.openlocfilehash: d28991254fba73de7a55135844d16417580d8792
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494389"
---
# <a name="icorprofilerthreadenum-interface"></a>ICorProfilerThreadEnum (Interfaz)
Proporciona métodos para iterar secuencialmente por una colección de subprocesos en Common Language Runtime.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](icorprofilerthreadenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerThreadEnum`.|  
|[Método GetCount](icorprofilerthreadenum-getcount-method.md)|Obtiene el número de subprocesos utilizados por la aplicación.|  
|[Next (Método)](icorprofilerthreadenum-next-method.md)|Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.|  
|[Reset (Método)](icorprofilerthreadenum-reset-method.md)|Mueve el cursor del enumerador a la posición inicial de la secuencia.|  
|[Método Skip](icorprofilerthreadenum-skip-method.md)|Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorProfilerThreadEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
