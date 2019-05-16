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
ms.openlocfilehash: 66bd56a332dc34fd35f3129256cc0e3d6c5d4508
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636699"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc (Método)

Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.

## <a name="syntax"></a>Sintaxis

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a>Parámetros

`cb`\
[in] El número de bytes que se asignan para el cuerpo del método.

## <a name="remarks"></a>Comentarios

 Se iniciará la memoria asignada en una dirección mayor que la dirección base del módulo que está asociado con este asignador. En otras palabras, cada asignador se crea para un módulo determinado y se intentará asignar memoria en un desplazamiento positivo desde su dirección base. Si `Alloc` no puede asignar el número solicitado de bytes en una dirección mayor que la dirección base del módulo, devuelve E_OUTOFMEMORY, independientemente de la cantidad de espacio de memoria disponible.

 El `Alloc` método debe usarse junto con el [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) método.

## <a name="requirements"></a>Requisitos
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado**: CorProf.idl, CorProf.h

 **Biblioteca:** CorGuids.lib

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMethodMalloc (interfaz)](imethodmalloc-interface.md)
