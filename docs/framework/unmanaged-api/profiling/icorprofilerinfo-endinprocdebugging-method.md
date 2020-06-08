---
title: ICorProfilerInfo::EndInprocDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: afbb007b6293e6e9cff92281a6f5e93b1e7924ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502982"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="b8e64-102">ICorProfilerInfo::EndInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="b8e64-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="b8e64-103">Cierra una sesión de depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="b8e64-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="b8e64-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="b8e64-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e64-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e64-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e64-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8e64-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="b8e64-107">de Valor que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="b8e64-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="b8e64-108">Este valor debe ser el mismo que el recibido en el método [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8e64-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8e64-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8e64-109">Remarks</span></span>  
 <span data-ttu-id="b8e64-110">Debe llamar a [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) y `EndInprocDebugging` dentro del mismo método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b8e64-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="b8e64-111">Los servicios de depuración de CLR admiten la depuración limitada en proceso en las .NET Framework versiones 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="b8e64-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="b8e64-112">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="b8e64-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b8e64-113">Sin embargo, debido a los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b8e64-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e64-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e64-114">Requirements</span></span>  
 <span data-ttu-id="b8e64-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e64-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e64-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8e64-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8e64-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8e64-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e64-118">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="b8e64-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e64-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b8e64-119">See also</span></span>

- [<span data-ttu-id="b8e64-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e64-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
