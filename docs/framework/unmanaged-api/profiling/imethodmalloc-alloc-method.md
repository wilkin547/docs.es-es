---
description: 'Más información sobre: IMethodMalloc:: Alloc (método)'
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
ms.openlocfilehash: f8a41530e0e1a126fafa1816e6fed58d10df6587
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736959"
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

## <a name="remarks"></a>Observaciones

 La memoria asignada comenzará en una dirección mayor que la dirección base del módulo que está asociado a este asignador. En otras palabras, cada asignador se crea para un módulo determinado e intentará asignar memoria en un desplazamiento positivo desde su dirección base. Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad real de espacio de memoria disponible.

 El `Alloc` método se debe usar junto con el método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) .

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** CorProf.idl, CorProf.h

 **Biblioteca:** CorGuids.lib

 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMethodMalloc (Interfaz)](imethodmalloc-interface.md)
