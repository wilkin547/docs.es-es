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
# <a name="icorprofilerinfo11getenvironmentvariable-method"></a><span data-ttu-id="b8fe8-103">ICorProfilerInfo11:: GetEnvironmentVariable (método)</span><span class="sxs-lookup"><span data-stu-id="b8fe8-103">ICorProfilerInfo11::GetEnvironmentVariable Method</span></span>

<span data-ttu-id="b8fe8-104">Obtiene una variable de entorno del proceso.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-104">Gets an environment variable from the process.</span></span> <span data-ttu-id="b8fe8-105">En plataformas que no son de Windows, el tiempo de ejecución mantiene una memoria caché interna de variables de entorno para garantizar la seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-105">On non-Windows platforms the runtime keeps an internal cache of environment variables to ensure thread safety.</span></span> <span data-ttu-id="b8fe8-106">Esto significa que, al llamar a `getenv` , no se leerán las variables de entorno nuevas o actualizadas establecidas por el código administrado que se ejecuta en el proceso después del inicio.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-106">This means that calling `getenv` will not read any new or updated environment variables set by managed code running in the process after startup.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b8fe8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8fe8-107">Syntax</span></span>  
  
```cpp  
    HRESULT GetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in]         ULONG cchValue,
                [out]        ULONG *pcchValue,
                [out, annotation("_Out_writes_to_(cchValue, *pcchValue)")]
                             WCHAR szValue[]);
```  
  
## <a name="parameters"></a><span data-ttu-id="b8fe8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8fe8-108">Parameters</span></span>

<span data-ttu-id="b8fe8-109">`szName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre de la variable de entorno que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-109">`szName` [in] A pointer to a null terminated wide character string containing the name of the environment variable to get.</span></span>

<span data-ttu-id="b8fe8-110">`cchValue` de La longitud, en caracteres, de `szValue` .</span><span class="sxs-lookup"><span data-stu-id="b8fe8-110">`cchValue` [in] The length, in characters, of `szValue`.</span></span>

<span data-ttu-id="b8fe8-111">`pcchValue` enuncia Puntero a la longitud total de caracteres de `szValue` .</span><span class="sxs-lookup"><span data-stu-id="b8fe8-111">`pcchValue` [out] A pointer to the total character length of `szValue`.</span></span>

<span data-ttu-id="b8fe8-112">`szValue` enuncia Un llamador proporcionó un búfer de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-112">`szValue` [out] A caller provided wide character buffer.</span></span> <span data-ttu-id="b8fe8-113">Cuando la función devuelve el búfer contendrá el valor de la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="b8fe8-113">When the function returns the buffer will contain the value of the environment variable.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8fe8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8fe8-114">Requirements</span></span>  

<span data-ttu-id="b8fe8-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="b8fe8-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="b8fe8-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8fe8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="b8fe8-117">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8fe8-117">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fe8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8fe8-118">See also</span></span>

- [<span data-ttu-id="b8fe8-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b8fe8-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b8fe8-120">Interfaz ICorProfilerInfo11</span><span class="sxs-lookup"><span data-stu-id="b8fe8-120">ICorProfilerInfo11 Interface</span></span>](icorprofilerinfo11-interface.md)
