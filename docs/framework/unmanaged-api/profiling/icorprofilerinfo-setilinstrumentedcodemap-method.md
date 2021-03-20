---
description: 'Más información acerca de: ICorProfilerInfo:: SetILInstrumentedCodeMap ((método)'
title: ICorProfilerInfo::SetILInstrumentedCodeMap (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: f9ed01b91f740a8bd95f4ad049076feb02363b8f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760397"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap (Método)

Establece un mapa de código para la función especificada utilizando las entradas de asignación del lenguaje intermedio de Microsoft (MSIL) especificadas.

> [!NOTE]
> En la .NET Framework versión 2,0, la llamada a `SetILInstrumentedCodeMap` `FunctionID` que representa una función genérica en un dominio de aplicación determinado afectará a todas las instancias de esa función en el dominio de aplicación.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>Parámetros

`functionId` de IDENTIFICADOR de la función para la que se va a establecer el mapa de código.

`fStartJit` de Valor booleano que indica si la llamada al `SetILInstrumentedCodeMap` método es la primera para un determinado `FunctionID` . Establezca `fStartJit` en `true` en la primera llamada a `SetILInstrumentedCodeMap` para un determinado `FunctionID` y, a `false` partir de ese momento,.

`cILMapEntries` de Número de elementos de la `cILMapEntries` matriz.

`rgILMapEntries` de Matriz de estructuras de COR_IL_MAP, cada una de las cuales especifica un desplazamiento de MSIL.

## <a name="remarks"></a>Observaciones

A menudo, un generador de perfiles inserta instrucciones dentro del código fuente de un método para instrumentar ese método (por ejemplo, para notificar cuando se alcanza una línea de código fuente determinada). `SetILInstrumentedCodeMap` permite a un generador de perfiles asignar las instrucciones de MSIL originales a sus nuevas ubicaciones. Un generador de perfiles puede utilizar el método [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) para obtener el desplazamiento de MSIL original para un desplazamiento nativo determinado.

El depurador asumirá que cada desplazamiento anterior se refiere a un desplazamiento de MSIL en el código MSIL original, sin modificar, y que cada nuevo desplazamiento hace referencia al desplazamiento de MSIL en el nuevo código instrumentado. La asignación debe ordenarse en orden ascendente. Para que funcione correctamente, siga estas instrucciones:

- No reordene el código MSIL instrumentado.

- No quite el código MSIL original.

- Incluya entradas para todos los puntos de secuencia del archivo de base de datos de programa (PDB) en el mapa. La asignación no interpola las entradas que faltan. Por lo tanto, dada la siguiente asignación:

  (0 Old, 0 nuevo)

  (5 antiguos, 10 nuevos)

  (9 antiguos, 20 nuevos)

  - Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará al nuevo desplazamiento 0.

  - Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.

  - Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.

  - Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.

  - Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.

  - Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.

En el .NET Framework 3,5 y versiones anteriores, se asigna la `rgILMapEntries` matriz mediante una llamada al método [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) . Dado que el tiempo de ejecución toma la propiedad de esta memoria, el generador de perfiles no debe intentar liberarla.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
