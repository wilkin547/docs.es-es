---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeGetProviderInfo (método)'
title: 'ICorProfilerInfo12:: EventPipeGetProviderInfo (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeGetProviderInfo
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7bc7ffe1c31e88dc1c65f1670f9bd179e732abfe
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805706"
---
# <a name="icorprofilerinfo12eventpipegetproviderinfo-method"></a><span data-ttu-id="d9646-103">ICorProfilerInfo12:: EventPipeGetProviderInfo (método)</span><span class="sxs-lookup"><span data-stu-id="d9646-103">ICorProfilerInfo12::EventPipeGetProviderInfo Method</span></span>

<span data-ttu-id="d9646-104">Crea un proveedor EventPipe que el generador de perfiles puede usar para escribir eventos para que los reciban otros agentes de escucha de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="d9646-104">Creates an EventPipe provider that the profiler can use to write events for other EventPipe listeners to receive.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d9646-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9646-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeGetProviderInfo(
                [in] EVENTPIPE_PROVIDER provider,
                [in]  ULONG      cchName,
                [out] ULONG      *pcchName,
                [out, annotation("_Out_writes_to_(cchName, *pcchName)")]
                      WCHAR      providerName[]);
```  
  
## <a name="parameters"></a><span data-ttu-id="d9646-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9646-106">Parameters</span></span>

<span data-ttu-id="d9646-107">`provider` de IDENTIFICADOR del proveedor para el que se va a proporcionar el nombre.</span><span class="sxs-lookup"><span data-stu-id="d9646-107">`provider` [in] The ID of the provider to provide the name for.</span></span>

<span data-ttu-id="d9646-108">`cchName` de Tamaño, en caracteres, de `providerName` .</span><span class="sxs-lookup"><span data-stu-id="d9646-108">`cchName` [in] The size, in characters, of `providerName`.</span></span>

<span data-ttu-id="d9646-109">`pcchName` enuncia Puntero a la longitud total de caracteres de `providerName` .</span><span class="sxs-lookup"><span data-stu-id="d9646-109">`pcchName` [out] A pointer to the total character length of `providerName`.</span></span>

<span data-ttu-id="d9646-110">`providerName` enuncia Un llamador proporcionó un búfer de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="d9646-110">`providerName` [out] A caller provided wide character buffer.</span></span> <span data-ttu-id="d9646-111">Cuando la función devuelva el búfer contendrá el nombre del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d9646-111">When the function returns the buffer will contain the name of the provider.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9646-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9646-112">Requirements</span></span>  

<span data-ttu-id="d9646-113">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d9646-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="d9646-114">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9646-114">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9646-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9646-115">See also</span></span>

- [<span data-ttu-id="d9646-116">Información general sobre EventPipe</span><span class="sxs-lookup"><span data-stu-id="d9646-116">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="d9646-117">EventProviders conocidos</span><span class="sxs-lookup"><span data-stu-id="d9646-117">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="d9646-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9646-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d9646-119">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="d9646-119">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="d9646-120">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="d9646-120">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
