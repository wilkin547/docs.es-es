---
description: 'Más información acerca de: ICLRRuntimeInfo:: IsStarted ((método)'
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
ms.openlocfilehash: 22059ecbded9eae9659cdaae8b9b92f2d7df0650
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753853"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="33463-103">ICLRRuntimeInfo::IsStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="33463-103">ICLRRuntimeInfo::IsStarted Method</span></span>

<span data-ttu-id="33463-104">Indica si se ha iniciado el Runtime (es decir, si se ha llamado al [método ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) y se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="33463-104">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33463-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33463-105">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33463-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33463-106">Parameters</span></span>  

 `pbStarted`  
 <span data-ttu-id="33463-107">[out] `true` Si se inicia este Runtime; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="33463-107">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="33463-108">enuncia Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33463-108">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33463-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33463-109">Return Value</span></span>  

 <span data-ttu-id="33463-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="33463-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="33463-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33463-111">HRESULT</span></span>|<span data-ttu-id="33463-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="33463-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33463-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="33463-113">S_OK</span></span>|<span data-ttu-id="33463-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="33463-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="33463-115">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="33463-115">E_NOTIMPL</span></span>|<span data-ttu-id="33463-116">La versión de Common Language Runtime (CLR) es anterior a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="33463-116">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33463-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33463-117">Remarks</span></span>  

 <span data-ttu-id="33463-118">Este método no funciona con las versiones de CLR anteriores a la versión de CLR en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="33463-118">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33463-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33463-119">Requirements</span></span>  

 <span data-ttu-id="33463-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33463-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33463-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="33463-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="33463-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33463-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33463-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33463-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33463-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="33463-124">See also</span></span>

- [<span data-ttu-id="33463-125">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33463-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="33463-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="33463-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="33463-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="33463-127">Hosting</span></span>](index.md)
