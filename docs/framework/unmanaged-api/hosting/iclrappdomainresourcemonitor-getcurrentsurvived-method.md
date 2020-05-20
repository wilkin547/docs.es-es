---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
ms.openlocfilehash: a73c0731c79dea3a0c411fe27a864ec9ac4e20b2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616026"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="dc696-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)</span><span class="sxs-lookup"><span data-stu-id="dc696-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="dc696-103">Obtiene el número de bytes que sobrevivieron a la última recolección completa de elementos no utilizados bloqueada y a la que hace referencia el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="dc696-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc696-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc696-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc696-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc696-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="dc696-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="dc696-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="dc696-107">enuncia Puntero al número de bytes que sobrevivieron después de la última recolección de elementos no utilizados retenida por este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc696-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="dc696-108">Después de una recolección completa, este número es preciso y completo.</span><span class="sxs-lookup"><span data-stu-id="dc696-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="dc696-109">Después de una recolección efímera, este número puede estar incompleto.</span><span class="sxs-lookup"><span data-stu-id="dc696-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="dc696-110">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="dc696-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="dc696-111">enuncia Puntero al número total de bytes que sobrevivieron de la última recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="dc696-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="dc696-112">Después de una recolección completa, este número representa el número de bytes que se encuentran en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="dc696-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="dc696-113">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="dc696-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="dc696-114">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="dc696-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc696-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc696-115">Return Value</span></span>  
 <span data-ttu-id="dc696-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="dc696-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dc696-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc696-117">HRESULT</span></span>|<span data-ttu-id="dc696-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc696-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc696-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc696-119">S_OK</span></span>|<span data-ttu-id="dc696-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc696-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="dc696-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="dc696-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="dc696-122">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="dc696-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc696-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dc696-123">Remarks</span></span>  
 <span data-ttu-id="dc696-124">Las estadísticas se actualizan solo después de una recolección completa de elementos no utilizados de bloqueo; es decir, una colección que incluye todas las generaciones y que detiene la aplicación mientras se produce la recolección.</span><span class="sxs-lookup"><span data-stu-id="dc696-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="dc696-125">Por ejemplo, la <xref:System.GC.Collect?displayProperty=nameWithType> sobrecarga del método realiza una colección completa de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="dc696-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="dc696-126">La recolección de elementos no utilizados simultánea se produce en segundo plano y no bloquea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc696-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="dc696-127">El `GetCurrentSurvived` método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dc696-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc696-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc696-128">Requirements</span></span>  
 <span data-ttu-id="dc696-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc696-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc696-130">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="dc696-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dc696-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc696-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc696-132">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc696-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc696-133">Consulta también</span><span class="sxs-lookup"><span data-stu-id="dc696-133">See also</span></span>

- [<span data-ttu-id="dc696-134">ICLRAppDomainResourceMonitor (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc696-134">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="dc696-135">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="dc696-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="dc696-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dc696-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="dc696-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="dc696-137">Hosting</span></span>](index.md)
