---
title: IValidator::FormatEventInfo (Método)
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31329a8674a9991a3f306eeff44ee3437ad64a5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779433"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="2aab9-102">IValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="2aab9-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="2aab9-103">Obtiene el mensaje de error correspondiente al error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="2aab9-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aab9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2aab9-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aab9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2aab9-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="2aab9-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="2aab9-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="2aab9-107">[in] Un `VEContext` instancia que contiene información contextual sobre el error de validación.</span><span class="sxs-lookup"><span data-stu-id="2aab9-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="2aab9-108">[in, out] Una cadena que contiene el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="2aab9-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="2aab9-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2aab9-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="2aab9-110">[in] Una matriz segura que contiene parámetros adicionales que describe el error.</span><span class="sxs-lookup"><span data-stu-id="2aab9-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aab9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aab9-111">Requirements</span></span>  
 <span data-ttu-id="2aab9-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aab9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aab9-113">**Encabezado**: IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="2aab9-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="2aab9-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2aab9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2aab9-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aab9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
