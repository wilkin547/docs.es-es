---
title: ICorProfilerInfo::BeginInprocDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: f0b118ef109d0adb17a28b60c091390b8e4280c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498666"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="ee159-102">ICorProfilerInfo::BeginInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="ee159-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="ee159-103">Inicializa la compatibilidad con la depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="ee159-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="ee159-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="ee159-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee159-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee159-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee159-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee159-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="ee159-107">de Establezca este valor en `true` para inicializar la compatibilidad con la depuración solo para el subproceso actual; establézcalo en `false` para inicializar la compatibilidad de depuración para todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ee159-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="ee159-108">enuncia Puntero a un valor devuelto que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="ee159-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee159-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee159-109">Remarks</span></span>  
 <span data-ttu-id="ee159-110">Los servicios de depuración de CLR admiten la depuración limitada en proceso en las .NET Framework versiones 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="ee159-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="ee159-111">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="ee159-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="ee159-112">Sin embargo, debido a los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ee159-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee159-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee159-113">Requirements</span></span>  
 <span data-ttu-id="ee159-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee159-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee159-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee159-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee159-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee159-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee159-117">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="ee159-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee159-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ee159-118">See also</span></span>

- [<span data-ttu-id="ee159-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee159-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
