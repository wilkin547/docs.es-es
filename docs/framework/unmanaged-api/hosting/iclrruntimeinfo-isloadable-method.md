---
title: ICLRRuntimeInfo::IsLoadable (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 13b4e00cf002abca625dbdda010f7d8994360687
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762544"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="9c39a-102">ICLRRuntimeInfo::IsLoadable (Método)</span><span class="sxs-lookup"><span data-stu-id="9c39a-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="9c39a-103">Indica si el tiempo de ejecución asociado a esta interfaz se puede cargar en el proceso actual, teniendo en cuenta otros tiempos de ejecución que podrían haberse cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9c39a-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c39a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c39a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c39a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c39a-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="9c39a-106">[out] `true` Si este Runtime se podría cargar en el proceso actual; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="9c39a-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c39a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9c39a-107">Return Value</span></span>  
 <span data-ttu-id="9c39a-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9c39a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9c39a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c39a-109">HRESULT</span></span>|<span data-ttu-id="9c39a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c39a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c39a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c39a-111">S_OK</span></span>|<span data-ttu-id="9c39a-112">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9c39a-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="9c39a-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9c39a-113">E_POINTER</span></span>|<span data-ttu-id="9c39a-114">`pbLoadable` es null.</span><span class="sxs-lookup"><span data-stu-id="9c39a-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c39a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c39a-115">Remarks</span></span>  
 <span data-ttu-id="9c39a-116">Si ya se ha cargado otro Runtime en el proceso y el tiempo de ejecución asociado a esta interfaz se puede cargar para la ejecución en paralelo en proceso, `pbLoadable` devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="9c39a-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="9c39a-117">Si los dos tiempos de ejecución no se pueden ejecutar en paralelo, `pbLoadable` devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="9c39a-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="9c39a-118">Por ejemplo, la versión 4 de Common Language Runtime (CLR) se puede ejecutar en paralelo en el mismo proceso con la versión de CLR 2,0 o la versión 1,1 de CLR.</span><span class="sxs-lookup"><span data-stu-id="9c39a-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="9c39a-119">Sin embargo, la versión de CLR 1,1 y la versión de CLR 2,0 no se pueden ejecutar en paralelo.</span><span class="sxs-lookup"><span data-stu-id="9c39a-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="9c39a-120">Si no se carga ningún Runtime en el proceso, este método siempre devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="9c39a-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c39a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c39a-121">Requirements</span></span>  
 <span data-ttu-id="9c39a-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c39a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c39a-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9c39a-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9c39a-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c39a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c39a-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c39a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c39a-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9c39a-126">See also</span></span>

- [<span data-ttu-id="9c39a-127">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c39a-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9c39a-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9c39a-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="9c39a-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9c39a-129">Hosting</span></span>](index.md)
