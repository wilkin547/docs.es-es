---
description: 'Más información sobre: ICorProfilerInfo11:: SetEnvironmentVariable (método)'
title: 'ICorProfilerInfo11:: SetEnvironmentVariable (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.SetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 77dc3fc992dec037881573323822dc11481a56be
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805614"
---
# <a name="icorprofilerinfo11setenvironmentvariable-method"></a>ICorProfilerInfo11:: SetEnvironmentVariable (método)

Establece una variable de entorno en el proceso. En plataformas que no son de Windows, el tiempo de ejecución mantiene una memoria caché interna de variables de entorno para garantizar la seguridad para subprocesos. Esto significa que si el generador de perfiles llama a `setenv` , el código administrado que se ejecuta en el proceso no recogerá la nueva variable de entorno.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT SetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in, string] const WCHAR *szValue);
```  
  
## <a name="parameters"></a>Parámetros

`szName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre de la variable de entorno que se va a establecer.

`szValue` de Puntero a una cadena de caracteres anchos terminada en null que contiene el valor de la variable de entorno que se va a establecer.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerInfo11](icorprofilerinfo11-interface.md)
