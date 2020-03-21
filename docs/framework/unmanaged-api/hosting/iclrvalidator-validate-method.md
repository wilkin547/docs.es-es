---
title: ICLRValidator::Validate (Método)
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178059"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="f6263-102">ICLRValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="f6263-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="f6263-103">Valida el ejecutable portátil (PE) o el lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f6263-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6263-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="f6263-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6263-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="f6263-106">[en] Puntero a `IVEHandler` una instancia que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f6263-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="f6263-107">[en] Identificador del <xref:System.AppDomain>archivo .</span><span class="sxs-lookup"><span data-stu-id="f6263-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="f6263-108">[en] Combinación de [valores ValidatorFlags,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) que indica el tipo de validación que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="f6263-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="f6263-109">[en] El número máximo de errores que se permiten antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="f6263-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="f6263-110">[in] Sin utilizar.</span><span class="sxs-lookup"><span data-stu-id="f6263-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f6263-111">[en] El nombre del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="f6263-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="f6263-112">[en] Un puntero al búfer de archivos.</span><span class="sxs-lookup"><span data-stu-id="f6263-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="f6263-113">[en] El tamaño, en bytes, del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="f6263-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6263-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6263-114">Return Value</span></span>  
  
|<span data-ttu-id="f6263-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6263-115">HRESULT</span></span>|<span data-ttu-id="f6263-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6263-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6263-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6263-117">S_OK</span></span>|<span data-ttu-id="f6263-118">`Validate`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="f6263-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="f6263-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6263-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6263-120">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6263-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6263-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6263-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6263-122">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f6263-122">The call timed out.</span></span>|  
|<span data-ttu-id="f6263-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6263-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6263-124">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="f6263-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6263-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6263-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6263-126">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="f6263-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6263-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6263-127">E_FAIL</span></span>|<span data-ttu-id="f6263-128">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="f6263-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6263-129">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f6263-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6263-130">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6263-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6263-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6263-131">Requirements</span></span>  
 <span data-ttu-id="f6263-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6263-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6263-133">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f6263-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f6263-134">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6263-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6263-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6263-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6263-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6263-136">See also</span></span>

- [<span data-ttu-id="f6263-137">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6263-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
