---
title: ICLRRuntimeInfo::IsStarted (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 85a7adddf395e07297c8fb6ceab4aa81e0aaf012
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762206"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="e624e-102">ICLRRuntimeInfo::IsStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="e624e-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="e624e-103">Indica si se ha iniciado el Runtime (es decir, si se ha llamado al [método ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) y se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="e624e-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e624e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e624e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e624e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e624e-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="e624e-106">[out] `true` Si se inicia este Runtime; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e624e-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="e624e-107">enuncia Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e624e-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e624e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e624e-108">Return Value</span></span>  
 <span data-ttu-id="e624e-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="e624e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e624e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e624e-110">HRESULT</span></span>|<span data-ttu-id="e624e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e624e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e624e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e624e-112">S_OK</span></span>|<span data-ttu-id="e624e-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e624e-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="e624e-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e624e-114">E_NOTIMPL</span></span>|<span data-ttu-id="e624e-115">La versión de Common Language Runtime (CLR) es anterior a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e624e-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e624e-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e624e-116">Remarks</span></span>  
 <span data-ttu-id="e624e-117">Este método no funciona con las versiones de CLR anteriores a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e624e-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e624e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e624e-118">Requirements</span></span>  
 <span data-ttu-id="e624e-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e624e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e624e-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e624e-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e624e-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e624e-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e624e-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e624e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e624e-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="e624e-123">See also</span></span>

- [<span data-ttu-id="e624e-124">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e624e-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e624e-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e624e-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e624e-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e624e-126">Hosting</span></span>](index.md)
