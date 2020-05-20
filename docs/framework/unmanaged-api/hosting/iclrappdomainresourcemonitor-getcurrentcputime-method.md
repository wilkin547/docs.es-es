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
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616039"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="b8e4b-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)</span><span class="sxs-lookup"><span data-stu-id="b8e4b-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="b8e4b-103">Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8e4b-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="b8e4b-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="b8e4b-107">enuncia Puntero al tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="b8e4b-108">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8e4b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8e4b-109">Return Value</span></span>  
  
|<span data-ttu-id="b8e4b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8e4b-110">HRESULT</span></span>|<span data-ttu-id="b8e4b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e4b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8e4b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8e4b-112">S_OK</span></span>|<span data-ttu-id="b8e4b-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="b8e4b-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="b8e4b-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="b8e4b-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="b8e4b-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8e4b-116">E_FAIL</span></span>|<span data-ttu-id="b8e4b-117">La supervisión de recursos del dominio de aplicación no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="b8e4b-118">o bien</span><span class="sxs-lookup"><span data-stu-id="b8e4b-118">-or-</span></span><br /><br /> <span data-ttu-id="b8e4b-119">Todos los demás errores.</span><span class="sxs-lookup"><span data-stu-id="b8e4b-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8e4b-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8e4b-120">Remarks</span></span>  
 <span data-ttu-id="b8e4b-121">Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b8e4b-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e4b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e4b-122">Requirements</span></span>  
 <span data-ttu-id="b8e4b-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e4b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e4b-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b8e4b-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b8e4b-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8e4b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8e4b-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e4b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e4b-127">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b8e4b-127">See also</span></span>

- [<span data-ttu-id="b8e4b-128">ICLRAppDomainResourceMonitor (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e4b-128">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="b8e4b-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b8e4b-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b8e4b-130">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="b8e4b-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="b8e4b-131">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b8e4b-131">Hosting</span></span>](index.md)
