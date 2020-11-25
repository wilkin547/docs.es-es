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
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714892"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="a1d90-102">ICLRRuntimeInfo::IsStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a1d90-102">ICLRRuntimeInfo::IsStarted Method</span></span>

<span data-ttu-id="a1d90-103">Indica si se ha iniciado el Runtime (es decir, si se ha llamado al [método ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) y se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="a1d90-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1d90-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1d90-105">Parameters</span></span>  

 `pbStarted`  
 <span data-ttu-id="a1d90-106">[out] `true` Si se inicia este Runtime; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="a1d90-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="a1d90-107">enuncia Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1d90-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1d90-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1d90-108">Return Value</span></span>  

 <span data-ttu-id="a1d90-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a1d90-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a1d90-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1d90-110">HRESULT</span></span>|<span data-ttu-id="a1d90-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1d90-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1d90-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1d90-112">S_OK</span></span>|<span data-ttu-id="a1d90-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1d90-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a1d90-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a1d90-114">E_NOTIMPL</span></span>|<span data-ttu-id="a1d90-115">La versión de Common Language Runtime (CLR) es anterior a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a1d90-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1d90-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1d90-116">Remarks</span></span>  

 <span data-ttu-id="a1d90-117">Este método no funciona con las versiones de CLR anteriores a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a1d90-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d90-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1d90-118">Requirements</span></span>  

 <span data-ttu-id="a1d90-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1d90-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d90-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a1d90-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a1d90-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1d90-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1d90-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d90-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d90-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1d90-123">See also</span></span>

- [<span data-ttu-id="a1d90-124">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1d90-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a1d90-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a1d90-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a1d90-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a1d90-126">Hosting</span></span>](index.md)
