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
ms.openlocfilehash: 9117a82dff48dcda8d96f0feb7b8c4a001fa17f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205880"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="f23ae-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f23ae-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="f23ae-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="f23ae-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f23ae-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f23ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f23ae-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="f23ae-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f23ae-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="f23ae-107">[in] Un `VEContext` instancia que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f23ae-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="f23ae-108">[in, out] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f23ae-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="f23ae-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f23ae-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="f23ae-110">[in] Una matriz segura de parámetros adicionales que se usarán en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f23ae-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f23ae-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f23ae-111">Return Value</span></span>  
  
|<span data-ttu-id="f23ae-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f23ae-112">HRESULT</span></span>|<span data-ttu-id="f23ae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f23ae-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f23ae-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f23ae-114">S_OK</span></span>|<span data-ttu-id="f23ae-115">`FormatEventInfo` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f23ae-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="f23ae-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f23ae-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f23ae-117">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f23ae-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f23ae-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f23ae-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f23ae-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f23ae-119">The call timed out.</span></span>|  
|<span data-ttu-id="f23ae-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f23ae-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f23ae-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f23ae-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f23ae-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f23ae-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f23ae-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="f23ae-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f23ae-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f23ae-124">E_FAIL</span></span>|<span data-ttu-id="f23ae-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="f23ae-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f23ae-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f23ae-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f23ae-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f23ae-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f23ae-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f23ae-128">Requirements</span></span>  
 <span data-ttu-id="f23ae-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f23ae-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23ae-130">**Encabezado**: IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f23ae-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f23ae-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f23ae-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f23ae-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f23ae-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23ae-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f23ae-133">See also</span></span>

- [<span data-ttu-id="f23ae-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f23ae-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="f23ae-135">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f23ae-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
