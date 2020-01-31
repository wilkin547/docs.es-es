---
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
ms.openlocfilehash: 99e473268fd0d5bb8ce120b97576277949b86508
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869002"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap (Método)

Establece un mapa de código para la función especificada utilizando las entradas de asignación del lenguaje intermedio de Microsoft (MSIL) especificadas.

> [!NOTE]
> En la .NET Framework versión 2,0, la llamada a `SetILInstrumentedCodeMap` en un `FunctionID` que representa una función genérica en un dominio de aplicación determinado afectará a todas las instancias de esa función en el dominio de aplicación.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>Parameters

`functionId`\
de IDENTIFICADOR de la función para la que se va a establecer el mapa de código.

`fStartJit`\
de Valor booleano que indica si la llamada al método `SetILInstrumentedCodeMap` es la primera para un `FunctionID`determinado. Establezca `fStartJit` en `true` en la primera llamada a `SetILInstrumentedCodeMap` para un `FunctionID`determinado y `false` después.

`cILMapEntries`\
de Número de elementos de la matriz de `cILMapEntries`.

`rgILMapEntries`\
de Matriz de estructuras de COR_IL_MAP, cada una de las cuales especifica un desplazamiento de MSIL.

## <a name="remarks"></a>Notas

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

En el .NET Framework 3,5 y versiones anteriores, asigna la matriz de `rgILMapEntries` llamando al método [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) . Dado que el tiempo de ejecución toma la propiedad de esta memoria, el generador de perfiles no debe intentar liberarla.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
