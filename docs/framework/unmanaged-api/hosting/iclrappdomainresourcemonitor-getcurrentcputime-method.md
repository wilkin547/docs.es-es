---
description: 'Más información sobre: ICLRAppDomainResourceMonitor:: Getcurrentcputime ((método)'
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
ms.openlocfilehash: ce36bf4ab88f953834d3ff12404bcaadcb42812d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753934"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="0ecdb-103">ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)</span><span class="sxs-lookup"><span data-stu-id="0ecdb-103">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>

<span data-ttu-id="0ecdb-104">Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-104">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ecdb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ecdb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ecdb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ecdb-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="0ecdb-107">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-107">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="0ecdb-108">enuncia Puntero al tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-108">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="0ecdb-109">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-109">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ecdb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ecdb-110">Return Value</span></span>  
  
|<span data-ttu-id="0ecdb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ecdb-111">HRESULT</span></span>|<span data-ttu-id="0ecdb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ecdb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ecdb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ecdb-113">S_OK</span></span>|<span data-ttu-id="0ecdb-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="0ecdb-115">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="0ecdb-115">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="0ecdb-116">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-116">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="0ecdb-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ecdb-117">E_FAIL</span></span>|<span data-ttu-id="0ecdb-118">La supervisión de recursos del dominio de aplicación no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-118">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="0ecdb-119">o bien</span><span class="sxs-lookup"><span data-stu-id="0ecdb-119">-or-</span></span><br /><br /> <span data-ttu-id="0ecdb-120">Todos los demás errores.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-120">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ecdb-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ecdb-121">Remarks</span></span>  

 <span data-ttu-id="0ecdb-122">Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0ecdb-122">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ecdb-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ecdb-123">Requirements</span></span>  

 <span data-ttu-id="0ecdb-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ecdb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ecdb-125">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0ecdb-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0ecdb-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ecdb-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ecdb-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ecdb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecdb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ecdb-128">See also</span></span>

- [<span data-ttu-id="0ecdb-129">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ecdb-129">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="0ecdb-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0ecdb-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0ecdb-131">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="0ecdb-131">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="0ecdb-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="0ecdb-132">Hosting</span></span>](index.md)
