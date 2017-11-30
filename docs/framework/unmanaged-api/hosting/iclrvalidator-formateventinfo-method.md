---
title: "ICLRValidator::FormatEventInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.FormatEventInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d03864ac8e4e0423e45ac084e01af98e3eab13a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="6ecaa-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="6ecaa-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="6ecaa-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecaa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ecaa-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ecaa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ecaa-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="6ecaa-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="6ecaa-107">[in] Un `VEContext` instancia que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="6ecaa-108">[entrada, salida] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="6ecaa-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="6ecaa-110">[in] Una matriz segura de parámetros adicionales que se utilizarán en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ecaa-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ecaa-111">Return Value</span></span>  
  
|<span data-ttu-id="6ecaa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ecaa-112">HRESULT</span></span>|<span data-ttu-id="6ecaa-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ecaa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ecaa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ecaa-114">S_OK</span></span>|<span data-ttu-id="6ecaa-115">`FormatEventInfo`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="6ecaa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ecaa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ecaa-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ecaa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ecaa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ecaa-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-119">The call timed out.</span></span>|  
|<span data-ttu-id="6ecaa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ecaa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ecaa-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ecaa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ecaa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ecaa-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ecaa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ecaa-124">E_FAIL</span></span>|<span data-ttu-id="6ecaa-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ecaa-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ecaa-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6ecaa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ecaa-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ecaa-128">Requirements</span></span>  
 <span data-ttu-id="6ecaa-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ecaa-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ecaa-130">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="6ecaa-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="6ecaa-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ecaa-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ecaa-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecaa-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecaa-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ecaa-133">See Also</span></span>  
 [<span data-ttu-id="6ecaa-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ecaa-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="6ecaa-135">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ecaa-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
