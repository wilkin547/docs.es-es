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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd7d5f66ef7c8f2b36b8dcb725b1931993c118dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526397"
---
# <a name="icorprofilerthreadenum-interface"></a>ICorProfilerThreadEnum (Interfaz)
Proporciona métodos para iterar secuencialmente por una colección de subprocesos en Common Language Runtime.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerThreadEnum`.|  
|[GetCount (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-getcount-method.md)|Obtiene el número de subprocesos utilizados por la aplicación.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-next-method.md)|Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-reset-method.md)|Mueve el cursor del enumerador a la posición inicial de la secuencia.|  
|[Skip (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-skip-method.md)|Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorProfilerThreadEnum` es un enumerador. Permite al receptor de una matriz extraer los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
