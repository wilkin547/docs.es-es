---
description: 'Más información sobre: ICorProfilerInfo11:: GetEnvironmentVariable (método)'
title: 'ICorProfilerInfo11:: GetEnvironmentVariable (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.GetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 635c5fb67b880c39f15fbc194a51a706d9ef7fe4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805836"
---
# <a name="icorprofilerinfo11getenvironmentvariable-method"></a>ICorProfilerInfo11:: GetEnvironmentVariable (método)

Obtiene una variable de entorno del proceso. En plataformas que no son de Windows, el tiempo de ejecución mantiene una memoria caché interna de variables de entorno para garantizar la seguridad para subprocesos. Esto significa que, al llamar a `getenv` , no se leerán las variables de entorno nuevas o actualizadas establecidas por el código administrado que se ejecuta en el proceso después del inicio.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT GetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in]         ULONG cchValue,
                [out]        ULONG *pcchValue,
                [out, annotation("_Out_writes_to_(cchValue, *pcchValue)")]
                             WCHAR szValue[]);
```  
  
## <a name="parameters"></a>Parámetros

`szName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre de la variable de entorno que se va a obtener.

`cchValue` de La longitud, en caracteres, de `szValue` .

`pcchValue` enuncia Puntero a la longitud total de caracteres de `szValue` .

`szValue` enuncia Un llamador proporcionó un búfer de caracteres anchos. Cuando la función devuelve el búfer contendrá el valor de la variable de entorno.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerInfo11](icorprofilerinfo11-interface.md)
