---
title: ICorProfilerObjectEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum
helpviewer_keywords: ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b46f33485a63404f11dc0606e420ec9c3c43f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum (Interfaz)
Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por el [Ngen.exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerObjectEnum`.|  
|[GetCount (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|Obtiene el número total de objetos inmovilizados en la colección.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|Obtiene el número especificado de objetos contiguos de una colección secuencial de módulos, comenzando en la posición del enumerador actual en la secuencia.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|Mueve el cursor de este enumerador a la posición inicial de la secuencia.|  
|[Skip (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|Desplaza el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorProfilerObjectEnum` es un enumerador. Permite al receptor de una matriz extraer los elementos del remitente a una velocidad que sea adecuada para el receptor. En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas relacionados con pasar matrices de gran tamaño como parámetros de método.  
  
 Use [ICorProfilerInfo2:: EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) para obtener un puntero a la `ICorProfilerObjectEnum` interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModuleFrozenObjects (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
