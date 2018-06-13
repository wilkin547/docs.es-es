---
title: IValidator::Validate (Método)
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf2c343db459879ca95372e104aee68b22dee6b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440622"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="5694c-102">IValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="5694c-102">IValidator::Validate Method</span></span>
<span data-ttu-id="5694c-103">Valida el archivo ejecutable portable (PE) especificado o el archivo de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5694c-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5694c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5694c-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5694c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5694c-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="5694c-106">[in] Un puntero a un `IVEHandler` instancia que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="5694c-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="5694c-107">[in] Un puntero al dominio de aplicación en el que se carga el archivo.</span><span class="sxs-lookup"><span data-stu-id="5694c-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="5694c-108">[in] Una combinación bit a bit de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indican las validaciones que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="5694c-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="5694c-109">[in] El número máximo de errores permitido antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="5694c-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="5694c-110">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="5694c-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="5694c-111">[in] Una cadena que especifica el nombre del archivo que se debe validar.</span><span class="sxs-lookup"><span data-stu-id="5694c-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="5694c-112">[in] Un puntero al búfer de memoria en el que se almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="5694c-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="5694c-113">[in] El tamaño, en bytes, del archivo que se debe validar.</span><span class="sxs-lookup"><span data-stu-id="5694c-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5694c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5694c-114">Requirements</span></span>  
 <span data-ttu-id="5694c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5694c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5694c-116">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="5694c-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="5694c-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5694c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5694c-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5694c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5694c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5694c-119">See Also</span></span>  
 
