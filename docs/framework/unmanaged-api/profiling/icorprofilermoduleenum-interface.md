---
description: 'Más información sobre: ICorProfilerModuleEnum (interfaz)'
title: ICorProfilerModuleEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 195379e9ad6bce94fc93465fe5e1418c5d8c076d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783825"
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum (Interfaz)

Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](icorprofilermoduleenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerModuleEnum`.|  
|[Método GetCount](icorprofilermoduleenum-getcount-method.md)|Obtiene el número de módulos administrados que se cargaron en la aplicación.|  
|[Next (método)](icorprofilermoduleenum-next-method.md)|Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.|  
|[Reset (Método)](icorprofilermoduleenum-reset-method.md)|Mueve el cursor del enumerador a la posición inicial de la secuencia.|  
|[Método Skip](icorprofilermoduleenum-skip-method.md)|Desplaza la posición del cursor del enumerador de manera que se omite el número especificado de elementos.|  
  
## <a name="remarks"></a>Observaciones  

 La interfaz `ICorProfilerModuleEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Método EnumModules](icorprofilerinfo3-enummodules-method.md)
