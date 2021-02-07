---
description: 'Más información acerca de: IValidator:: Validate (método)'
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
ms.openlocfilehash: 6df70274a788b949686fe2509b525c5a8b04089c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680023"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="78afa-103">IValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="78afa-103">IValidator::Validate Method</span></span>

<span data-ttu-id="78afa-104">Valida el archivo ejecutable portable (PE) o el archivo de lenguaje intermedio de Microsoft (MSIL) especificado.</span><span class="sxs-lookup"><span data-stu-id="78afa-104">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78afa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78afa-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="78afa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78afa-106">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="78afa-107">de Puntero a una `IVEHandler` instancia de que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="78afa-107">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="78afa-108">de Puntero al dominio de aplicación en el que se carga el archivo.</span><span class="sxs-lookup"><span data-stu-id="78afa-108">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="78afa-109">de Combinación bit a bit de valores de [ValidatorFlags (](validatorflags-enumeration.md) , que indica las validaciones que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="78afa-109">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="78afa-110">de Número máximo de errores que se permiten antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="78afa-110">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="78afa-111">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78afa-111">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="78afa-112">de Cadena que especifica el nombre del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="78afa-112">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="78afa-113">de Puntero al búfer de memoria en el que se almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="78afa-113">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="78afa-114">de Tamaño, en bytes, del archivo que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="78afa-114">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78afa-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78afa-115">Requirements</span></span>  

 <span data-ttu-id="78afa-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78afa-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78afa-117">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="78afa-117">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="78afa-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78afa-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78afa-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78afa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
