---
title: IMethodMalloc (Interfaz)
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447551"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc (Interfaz)
Proporciona un método para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).  
  
> [!NOTE]
> La interfaz de `IMethodMalloc` es un asignador de memoria simple. Permite asignar memoria, pero no para liberarla.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo. La memoria que está por encima de la base de un módulo puede ser precioso, por lo que se debe usar el asignador para asignar memoria solo para el cuerpo de una función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
