---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: de57fec05c338e51d0691ccfa0d0bffb334848de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126796"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="89567-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)</span><span class="sxs-lookup"><span data-stu-id="89567-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="89567-103">Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="89567-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89567-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89567-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89567-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89567-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="89567-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="89567-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="89567-107">enuncia Puntero al tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="89567-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="89567-108">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="89567-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89567-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89567-109">Return Value</span></span>  
  
|<span data-ttu-id="89567-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89567-110">HRESULT</span></span>|<span data-ttu-id="89567-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="89567-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89567-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="89567-112">S_OK</span></span>|<span data-ttu-id="89567-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="89567-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="89567-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="89567-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="89567-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="89567-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="89567-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89567-116">E_FAIL</span></span>|<span data-ttu-id="89567-117">La supervisión de recursos del dominio de aplicación no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="89567-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="89567-118">o bien</span><span class="sxs-lookup"><span data-stu-id="89567-118">-or-</span></span><br /><br /> <span data-ttu-id="89567-119">Todos los demás errores.</span><span class="sxs-lookup"><span data-stu-id="89567-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89567-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89567-120">Remarks</span></span>  
 <span data-ttu-id="89567-121">Este método es el equivalente no administrado de la propiedad <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> administrada.</span><span class="sxs-lookup"><span data-stu-id="89567-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89567-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89567-122">Requirements</span></span>  
 <span data-ttu-id="89567-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89567-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89567-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="89567-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="89567-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="89567-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89567-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89567-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89567-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="89567-127">See also</span></span>

- [<span data-ttu-id="89567-128">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89567-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="89567-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="89567-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="89567-130">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="89567-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="89567-131">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="89567-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
