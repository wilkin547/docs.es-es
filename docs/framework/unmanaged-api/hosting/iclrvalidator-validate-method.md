---
description: 'Más información sobre: ICLRValidator:: Validate (método)'
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
ms.openlocfilehash: a188315d44021fc8bf40be9bb9aecac436351467
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636750"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="56896-103">ICLRValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="56896-103">ICLRValidator::Validate Method</span></span>

<span data-ttu-id="56896-104">Valida el ejecutable portable (PE) o el lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="56896-104">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56896-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56896-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="56896-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56896-106">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="56896-107">de Puntero a una `IVEHandler` instancia de que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="56896-107">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="56896-108">de Identificador del actual <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="56896-108">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="56896-109">de Combinación de valores de [ValidatorFlags (](validatorflags-enumeration.md) , que indica el tipo de validación que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="56896-109">[in] A combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="56896-110">de Número máximo de errores que se permiten antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="56896-110">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="56896-111">[in] Sin utilizar.</span><span class="sxs-lookup"><span data-stu-id="56896-111">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="56896-112">de Nombre del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="56896-112">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="56896-113">de Puntero al búfer de archivos.</span><span class="sxs-lookup"><span data-stu-id="56896-113">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="56896-114">de Tamaño, en bytes, del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="56896-114">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56896-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56896-115">Return Value</span></span>  
  
|<span data-ttu-id="56896-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56896-116">HRESULT</span></span>|<span data-ttu-id="56896-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="56896-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56896-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="56896-118">S_OK</span></span>|<span data-ttu-id="56896-119">`Validate` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="56896-119">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="56896-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56896-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56896-121">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="56896-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56896-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56896-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56896-123">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="56896-123">The call timed out.</span></span>|  
|<span data-ttu-id="56896-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56896-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56896-125">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="56896-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56896-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56896-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56896-127">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="56896-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56896-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56896-128">E_FAIL</span></span>|<span data-ttu-id="56896-129">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="56896-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56896-130">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="56896-130">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56896-131">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56896-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56896-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56896-132">Requirements</span></span>  

 <span data-ttu-id="56896-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56896-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56896-134">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="56896-134">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="56896-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56896-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56896-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56896-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56896-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="56896-137">See also</span></span>

- [<span data-ttu-id="56896-138">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="56896-138">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
