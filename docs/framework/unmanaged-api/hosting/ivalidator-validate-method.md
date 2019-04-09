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
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127509"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="f92a1-102">IValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="f92a1-102">IValidator::Validate Method</span></span>
<span data-ttu-id="f92a1-103">Valida el archivo ejecutable portable (PE) especificado o el archivo de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f92a1-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f92a1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f92a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f92a1-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="f92a1-106">[in] Un puntero a un `IVEHandler` instancia que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f92a1-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="f92a1-107">[in] Un puntero al dominio de aplicación en el que se carga el archivo.</span><span class="sxs-lookup"><span data-stu-id="f92a1-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="f92a1-108">[in] Una combinación bit a bit de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indica las validaciones que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="f92a1-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="f92a1-109">[in] El número máximo de errores permitido antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="f92a1-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="f92a1-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f92a1-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f92a1-111">[in] Una cadena que especifica el nombre del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="f92a1-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="f92a1-112">[in] Un puntero al búfer de memoria donde se almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="f92a1-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="f92a1-113">[in] El tamaño, en bytes, del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="f92a1-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f92a1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f92a1-114">Requirements</span></span>  
 <span data-ttu-id="f92a1-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f92a1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f92a1-116">**Encabezado**: IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f92a1-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f92a1-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f92a1-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f92a1-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f92a1-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
