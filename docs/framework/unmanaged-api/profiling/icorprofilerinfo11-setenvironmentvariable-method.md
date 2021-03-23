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
# <a name="icorprofilerinfo11setenvironmentvariable-method"></a><span data-ttu-id="a42d2-103">ICorProfilerInfo11:: SetEnvironmentVariable (método)</span><span class="sxs-lookup"><span data-stu-id="a42d2-103">ICorProfilerInfo11::SetEnvironmentVariable Method</span></span>

<span data-ttu-id="a42d2-104">Establece una variable de entorno en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a42d2-104">Sets an environment variable in the process.</span></span> <span data-ttu-id="a42d2-105">En plataformas que no son de Windows, el tiempo de ejecución mantiene una memoria caché interna de variables de entorno para garantizar la seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a42d2-105">On non-Windows platforms the runtime keeps an internal cache of environment variables to ensure thread safety.</span></span> <span data-ttu-id="a42d2-106">Esto significa que si el generador de perfiles llama a `setenv` , el código administrado que se ejecuta en el proceso no recogerá la nueva variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="a42d2-106">This means that if the profiler calls `setenv` the new environment variable will not be picked up by managed code running in the process.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a42d2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a42d2-107">Syntax</span></span>  
  
```cpp  
    HRESULT SetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in, string] const WCHAR *szValue);
```  
  
## <a name="parameters"></a><span data-ttu-id="a42d2-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a42d2-108">Parameters</span></span>

<span data-ttu-id="a42d2-109">`szName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre de la variable de entorno que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="a42d2-109">`szName` [in] A pointer to a null terminated wide character string containing the name of the environment variable to set.</span></span>

<span data-ttu-id="a42d2-110">`szValue` de Puntero a una cadena de caracteres anchos terminada en null que contiene el valor de la variable de entorno que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="a42d2-110">`szValue` [in] A pointer to a null terminated wide character string containing the value of the environment variable to set.</span></span>

## <a name="requirements"></a><span data-ttu-id="a42d2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a42d2-111">Requirements</span></span>  

<span data-ttu-id="a42d2-112">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a42d2-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="a42d2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a42d2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a42d2-114">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a42d2-114">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42d2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a42d2-115">See also</span></span>

- [<span data-ttu-id="a42d2-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a42d2-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a42d2-117">Interfaz ICorProfilerInfo11</span><span class="sxs-lookup"><span data-stu-id="a42d2-117">ICorProfilerInfo11 Interface</span></span>](icorprofilerinfo11-interface.md)
