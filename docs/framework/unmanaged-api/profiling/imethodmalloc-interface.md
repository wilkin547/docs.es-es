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
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc (Interfaz)
Proporciona un método para asignar memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.  
  
> [!NOTE]
>  La `IMethodMalloc` interfaz es un asignador de memoria simple. Permite asignar memoria, pero no para liberarlo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Intenta asignar una cantidad específica de memoria para un nuevo cuerpo de función MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 Cada asignador es específico del módulo y garantiza que el cuerpo de función estará en un desplazamiento positivo de la base del módulo. La memoria por encima de la base de un módulo puede ser muy valiosa, por lo que debe usarse el asignador para asignar memoria sólo para un cuerpo de función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
