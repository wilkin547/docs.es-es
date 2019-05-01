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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969818"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc (Interfaz)
Proporciona un método para asignar memoria para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.  
  
> [!NOTE]
>  El `IMethodMalloc` interfaz es un asignador de memoria simple. Permite asignar memoria, pero no a lo libere.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo. Memoria por encima de la base de un módulo puede ser valioso, por lo que se debe usar el asignador para asignar memoria sólo para un cuerpo de función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
