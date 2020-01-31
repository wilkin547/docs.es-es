---
title: ICorProfilerObjectEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: fce89cc2b3b0104ba017b7df9105dea3f6ec4e91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868231"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum (Interfaz)
Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen. exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](icorprofilerobjectenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerObjectEnum`.|  
|[GetCount (método)](icorprofilerobjectenum-getcount-method.md)|Obtiene el número total de objetos inmovilizados de la colección.|  
|[Next (método)](icorprofilerobjectenum-next-method.md)|Obtiene el número especificado de objetos contiguos de una colección secuencial de objetos, empezando en la posición actual del enumerador en la secuencia.|  
|[Reset (método)](icorprofilerobjectenum-reset-method.md)|Mueve el cursor de este enumerador a la posición inicial de la secuencia.|  
|[Skip (método)](icorprofilerobjectenum-skip-method.md)|Hace avanzar el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.|  
  
## <a name="remarks"></a>Notas  
 La interfaz `ICorProfilerObjectEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor puede controlar explícitamente el flujo de elementos de la matriz, evitando así los problemas relacionados con el paso de matrices grandes como parámetros de método.  
  
 Use [ICorProfilerInfo2:: enummodulefrozenobjects (](icorprofilerinfo2-enummodulefrozenobjects-method.md) para obtener un puntero a la interfaz `ICorProfilerObjectEnum`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [EnumModuleFrozenObjects (método)](icorprofilerinfo2-enummodulefrozenobjects-method.md)
