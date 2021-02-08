---
description: 'Más información acerca de: ICorProfilerInfo:: Endinprocdebugging ((método)'
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
ms.openlocfilehash: 5e172abaa99e0a64031a9c1ec1beac5f23386d1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788623"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="db14c-103">ICorProfilerInfo::EndInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="db14c-103">ICorProfilerInfo::EndInprocDebugging Method</span></span>

<span data-ttu-id="db14c-104">Cierra una sesión de depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="db14c-104">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="db14c-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="db14c-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db14c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db14c-106">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db14c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db14c-107">Parameters</span></span>  

 `dwProfilerContext`  
 <span data-ttu-id="db14c-108">de Valor que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="db14c-108">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="db14c-109">Este valor debe ser el mismo que el recibido en el método [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db14c-109">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db14c-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db14c-110">Remarks</span></span>  

 <span data-ttu-id="db14c-111">Debe llamar a [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) y `EndInprocDebugging` dentro del mismo método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="db14c-111">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="db14c-112">Los servicios de depuración de CLR admiten la depuración limitada en proceso en las .NET Framework versiones 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="db14c-112">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="db14c-113">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="db14c-113">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="db14c-114">Sin embargo, debido a los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="db14c-114">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db14c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db14c-115">Requirements</span></span>  

 <span data-ttu-id="db14c-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db14c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db14c-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db14c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db14c-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db14c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db14c-119">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="db14c-119">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db14c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="db14c-120">See also</span></span>

- [<span data-ttu-id="db14c-121">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db14c-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
