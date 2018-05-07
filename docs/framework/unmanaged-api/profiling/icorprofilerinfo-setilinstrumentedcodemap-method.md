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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ecb80de1ae46b072df4bab8357e78e7a22ae298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap (Método)
Establece un mapa de código para la función especificada usando las entradas de mapa de lenguaje intermedio (MSIL) de Microsoft especificadas.  
  
> [!NOTE]
>  En .NET Framework versión 2.0, una llamada a `SetILInstrumentedCodeMap` en un `FunctionID` que representa un tipo genérico se funcionen en un dominio de aplicación determinado afectarán a todas las instancias de esa función en el dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para que se establecerá el mapa de código.  
  
 `fStartJit`  
 [in] Un valor booleano que indica si la llamada a la `SetILInstrumentedCodeMap` método es la primera para una determinada `FunctionID`. Establecer `fStartJit` a `true` en la primera llamada a `SetILInstrumentedCodeMap` para un determinado `FunctionID`y a `false` a partir de ahí.  
  
 `cILMapEntries`  
 [in] El número de elementos de la `cILMapEntries` matriz.  
  
 `rgILMapEntries`  
 [in] Una matriz de estructuras COR_IL_MAP, cada uno de los cuales especifica un desplazamiento MSIL.  
  
## <a name="remarks"></a>Comentarios  
 A menudo, un generador de perfiles inserta instrucciones incluidas en el código fuente de un método para instrumentar ese método (por ejemplo, para notificar cuando se alcanza una línea de código fuente). `SetILInstrumentedCodeMap` permite a un generador de perfiles asignar las instrucciones de MSIL originales a sus nuevas ubicaciones. Un generador de perfiles puede usar el [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) método para obtener el desplazamiento MSIL original de un desplazamiento nativo dado.  
  
 El depurador supondrá que cada desplazamiento anterior hace referencia a un desplazamiento dentro del código MSIL original, sin modificar de MSIL, y que cada nuevo desplazamiento hace referencia al desplazamiento de MSIL dentro del nuevo código instrumentado. La asignación se debe ordenar en orden ascendente. Para la ejecución paso a paso para que funcionen correctamente, siga estas instrucciones:  
  
-   No reordene el código MSIL instrumentado.  
  
-   No quite el código MSIL original.  
  
-   Incluya entradas para todos los puntos de secuencia del archivo de programa (PDB) de la base de datos en el mapa. El mapa no interpola las entradas que faltan. Por lo tanto, dado el mapa siguiente:  
  
     (0 anterior, 0 nuevo)  
  
     (5 anterior, 10 nueva)  
  
     (9 antiguo, 20 nueva)  
  
    -   Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignarán al nuevo desplazamiento de 0.  
  
    -   Un desplazamiento anterior de 5, 6, 7 u 8 se asignarán al nuevo desplazamiento de 10.  
  
    -   Un desplazamiento anterior de 9 o versiones posteriores se asignarán al nuevo desplazamiento de 20.  
  
    -   Se asignará un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al anterior desplazamiento de 0.  
  
    -   Un desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 nuevos se asignarán al anterior desplazamiento de 5.  
  
    -   Se asignará un nuevo desplazamiento de 20 o superior al anterior desplazamiento de 9.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
