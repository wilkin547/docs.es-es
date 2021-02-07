---
description: 'Más información acerca de: ICorProfilerFunctionEnum (interfaz)'
title: ICorProfilerFunctionEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 0a9437ee1f5c481c2c2d1fd46361da6e938dd179
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737602"
---
# <a name="icorprofilerfunctionenum-interface"></a>ICorProfilerFunctionEnum (Interfaz)

Proporciona métodos para iterar secuencialmente por una colección de funciones en Common Language Runtime.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](icorprofilerfunctionenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerFunctionEnum`.|  
|[Método GetCount](icorprofilerfunctionenum-getcount-method.md)|Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.|  
|[Next (método)](icorprofilerfunctionenum-next-method.md)|Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.|  
|[Reset (Método)](icorprofilerfunctionenum-reset-method.md)|Mueve el cursor del enumerador a la posición inicial de la secuencia.|  
|[Método Skip](icorprofilerfunctionenum-skip-method.md)|Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.|  
  
## <a name="remarks"></a>Observaciones  

 La interfaz `ICorProfilerFunctionEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.  
  
 `ICorProfilerFunctionEnum` enumera las funciones que ya se han compilado con JIT, pero no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen.exe.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Método EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)
