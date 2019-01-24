---
title: IMethodMalloc::Alloc (Método)
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54c38f9a9abc9a02ba4d84c9a41b2ef6b1f7cb69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528568"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc (Método)
Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cb`  
 [in] El número de bytes que se asignan para el cuerpo del método.  
  
## <a name="remarks"></a>Comentarios  
 Se iniciará la memoria asignada en una dirección mayor que la dirección base del módulo que está asociado con este asignador. En otras palabras, cada asignador se crea para un módulo determinado y se intentará asignar memoria en un desplazamiento positivo desde su dirección base. Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad de espacio de memoria disponible.  
  
 El `Alloc` método debe usarse junto con el [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** WindSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMethodMalloc (interfaz)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
