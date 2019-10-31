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
ms.openlocfilehash: 935d8e9fa3ed15be03c6cd05b1bc3c4919d0cc2b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127854"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="55cab-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="55cab-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="55cab-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="55cab-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55cab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55cab-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55cab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55cab-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="55cab-106">de Valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="55cab-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="55cab-107">de `VEContext` instancia de que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="55cab-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="55cab-108">[in, out] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="55cab-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="55cab-109">de La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="55cab-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="55cab-110">de Matriz segura de parámetros adicionales que se van a utilizar en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="55cab-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55cab-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55cab-111">Return Value</span></span>  
  
|<span data-ttu-id="55cab-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55cab-112">HRESULT</span></span>|<span data-ttu-id="55cab-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="55cab-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55cab-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="55cab-114">S_OK</span></span>|<span data-ttu-id="55cab-115">`FormatEventInfo` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="55cab-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="55cab-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55cab-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55cab-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="55cab-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55cab-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55cab-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55cab-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="55cab-119">The call timed out.</span></span>|  
|<span data-ttu-id="55cab-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55cab-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55cab-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="55cab-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55cab-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55cab-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55cab-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="55cab-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55cab-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55cab-124">E_FAIL</span></span>|<span data-ttu-id="55cab-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="55cab-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55cab-126">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="55cab-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55cab-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55cab-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55cab-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55cab-128">Requirements</span></span>  
 <span data-ttu-id="55cab-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55cab-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55cab-130">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="55cab-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="55cab-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55cab-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55cab-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55cab-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cab-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="55cab-133">See also</span></span>

- [<span data-ttu-id="55cab-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55cab-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="55cab-135">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55cab-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
