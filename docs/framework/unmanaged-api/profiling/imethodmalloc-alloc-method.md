---
title: "IMethodMalloc::Alloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26998e8b2e8648b4fb175f188540e7bc33c580c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc (Método)
Intenta asignar una cantidad específica de memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cb`  
 [in] El número de bytes que se va a asignar para el cuerpo del método.  
  
## <a name="remarks"></a>Comentarios  
 La memoria asignada comenzará en una dirección mayor que la dirección base del módulo que está asociado a este asignador. En otras palabras, cada asignador se crea para un módulo determinado e intentará asignar memoria en un desplazamiento positivo respecto a su dirección base. Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devolverá E_OUTOFMEMORY, independientemente de la cantidad real de espacio de memoria disponible.  
  
 El `Alloc` método debe utilizarse junto con la [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** WindSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMethodMalloc (interfaz)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
