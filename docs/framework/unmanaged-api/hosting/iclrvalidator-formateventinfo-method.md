---
title: ICLRValidator::FormatEventInfo (Método)
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30fca37887c17f5f0da7fd2faaba32f0e5edf235
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437370"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="1bd94-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="1bd94-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="1bd94-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="1bd94-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bd94-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bd94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bd94-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="1bd94-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="1bd94-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="1bd94-107">[in] Un `VEContext` instancia que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="1bd94-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="1bd94-108">[entrada, salida] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="1bd94-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="1bd94-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1bd94-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="1bd94-110">[in] Una matriz segura de parámetros adicionales que se utilizarán en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1bd94-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bd94-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1bd94-111">Return Value</span></span>  
  
|<span data-ttu-id="1bd94-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1bd94-112">HRESULT</span></span>|<span data-ttu-id="1bd94-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bd94-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1bd94-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bd94-114">S_OK</span></span>|<span data-ttu-id="1bd94-115">`FormatEventInfo` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bd94-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="1bd94-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1bd94-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1bd94-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bd94-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1bd94-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1bd94-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1bd94-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1bd94-119">The call timed out.</span></span>|  
|<span data-ttu-id="1bd94-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1bd94-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1bd94-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1bd94-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1bd94-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1bd94-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1bd94-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1bd94-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1bd94-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1bd94-124">E_FAIL</span></span>|<span data-ttu-id="1bd94-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1bd94-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1bd94-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1bd94-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1bd94-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1bd94-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1bd94-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bd94-128">Requirements</span></span>  
 <span data-ttu-id="1bd94-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bd94-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd94-130">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="1bd94-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="1bd94-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bd94-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bd94-132">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd94-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd94-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bd94-133">See Also</span></span>  
 [<span data-ttu-id="1bd94-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bd94-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="1bd94-135">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bd94-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
