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
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699149"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="226d3-102">IValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="226d3-102">IValidator::Validate Method</span></span>

<span data-ttu-id="226d3-103">Valida el archivo ejecutable portable (PE) o el archivo de lenguaje intermedio de Microsoft (MSIL) especificado.</span><span class="sxs-lookup"><span data-stu-id="226d3-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="226d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="226d3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="226d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="226d3-105">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="226d3-106">de Puntero a una `IVEHandler` instancia de que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="226d3-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="226d3-107">de Puntero al dominio de aplicación en el que se carga el archivo.</span><span class="sxs-lookup"><span data-stu-id="226d3-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="226d3-108">de Combinación bit a bit de valores de [ValidatorFlags (](validatorflags-enumeration.md) , que indica las validaciones que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="226d3-108">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="226d3-109">de Número máximo de errores que se permiten antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="226d3-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="226d3-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="226d3-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="226d3-111">de Cadena que especifica el nombre del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="226d3-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="226d3-112">de Puntero al búfer de memoria en el que se almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="226d3-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="226d3-113">de Tamaño, en bytes, del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="226d3-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="226d3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="226d3-114">Requirements</span></span>  

 <span data-ttu-id="226d3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="226d3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="226d3-116">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="226d3-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="226d3-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="226d3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="226d3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="226d3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
