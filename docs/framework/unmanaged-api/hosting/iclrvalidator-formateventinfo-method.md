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
ms.openlocfilehash: a3f52deab4d0c8ca56fae2e65912217e51abe58a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715880"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="47fc0-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="47fc0-102">ICLRValidator::FormatEventInfo Method</span></span>

<span data-ttu-id="47fc0-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="47fc0-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fc0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47fc0-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47fc0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47fc0-105">Parameters</span></span>  

 `hVECode`  
 <span data-ttu-id="47fc0-106">de Valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="47fc0-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="47fc0-107">de `VEContext` Instancia de que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="47fc0-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="47fc0-108">[in, out] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="47fc0-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="47fc0-109">de La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="47fc0-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="47fc0-110">de Matriz segura de parámetros adicionales que se van a utilizar en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="47fc0-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47fc0-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47fc0-111">Return Value</span></span>  
  
|<span data-ttu-id="47fc0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47fc0-112">HRESULT</span></span>|<span data-ttu-id="47fc0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="47fc0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47fc0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="47fc0-114">S_OK</span></span>|<span data-ttu-id="47fc0-115">`FormatEventInfo` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="47fc0-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="47fc0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47fc0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47fc0-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="47fc0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47fc0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47fc0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47fc0-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="47fc0-119">The call timed out.</span></span>|  
|<span data-ttu-id="47fc0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47fc0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47fc0-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="47fc0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47fc0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47fc0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47fc0-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="47fc0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47fc0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47fc0-124">E_FAIL</span></span>|<span data-ttu-id="47fc0-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="47fc0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47fc0-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="47fc0-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47fc0-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47fc0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47fc0-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47fc0-128">Requirements</span></span>  

 <span data-ttu-id="47fc0-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47fc0-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47fc0-130">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="47fc0-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="47fc0-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47fc0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47fc0-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47fc0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fc0-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47fc0-133">See also</span></span>

- [<span data-ttu-id="47fc0-134">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47fc0-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="47fc0-135">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47fc0-135">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
