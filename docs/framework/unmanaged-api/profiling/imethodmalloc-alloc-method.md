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
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721171"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc (Método)

Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).

## <a name="syntax"></a>Sintaxis

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parámetros

`cb`\
de Número de bytes que se van a asignar para el cuerpo del método.

## <a name="remarks"></a>Comentarios

 La memoria asignada comenzará en una dirección mayor que la dirección base del módulo que está asociado a este asignador. En otras palabras, cada asignador se crea para un módulo determinado e intentará asignar memoria en un desplazamiento positivo desde su dirección base. Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad real de espacio de memoria disponible.

 El `Alloc` método se debe usar junto con el método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) .

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** CorProf.idl, CorProf.h

 **Biblioteca:** CorGuids.lib

 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte también

- [IMethodMalloc (Interfaz)](imethodmalloc-interface.md)
