---
description: 'Más información acerca de: ICorProfilerObjectEnum (interfaz)'
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
ms.openlocfilehash: a41900c104818566704af0070a8cd3c6cf1bba8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781368"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum (Interfaz)

Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por el [Ngen.exe (generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Clone](icorprofilerobjectenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerObjectEnum`.|  
|[Método GetCount](icorprofilerobjectenum-getcount-method.md)|Obtiene el número total de objetos inmovilizados de la colección.|  
|[Next (método)](icorprofilerobjectenum-next-method.md)|Obtiene el número especificado de objetos contiguos de una colección secuencial de objetos, empezando en la posición actual del enumerador en la secuencia.|  
|[Reset (Método)](icorprofilerobjectenum-reset-method.md)|Mueve el cursor de este enumerador a la posición inicial de la secuencia.|  
|[Método Skip](icorprofilerobjectenum-skip-method.md)|Hace avanzar el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.|  
  
## <a name="remarks"></a>Observaciones  

 La interfaz `ICorProfilerObjectEnum` es un enumerador. Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor puede controlar explícitamente el flujo de elementos de la matriz, evitando así los problemas relacionados con el paso de matrices grandes como parámetros de método.  
  
 Use [ICorProfilerInfo2:: enummodulefrozenobjects (](icorprofilerinfo2-enummodulefrozenobjects-method.md) para obtener un puntero a la `ICorProfilerObjectEnum` interfaz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Método EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)
