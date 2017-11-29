---
title: IMethodMalloc (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc
helpviewer_keywords: IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d246f329f80a76d2c93190fd663c7362418385f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
