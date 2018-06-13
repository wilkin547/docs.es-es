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
ms.openlocfilehash: 875052ed26e83de50807e33e9c74dcf89f7ee679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440650"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="38f1f-102">IValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="38f1f-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="38f1f-103">Obtiene el mensaje de error correspondiente al error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="38f1f-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38f1f-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38f1f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38f1f-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="38f1f-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="38f1f-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="38f1f-107">[in] Un `VEContext` instancia que contiene información contextual sobre el error de validación.</span><span class="sxs-lookup"><span data-stu-id="38f1f-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="38f1f-108">[entrada, salida] Una cadena que contiene el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="38f1f-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="38f1f-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="38f1f-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="38f1f-110">[in] Una matriz segura que contiene los parámetros adicionales que describe el error.</span><span class="sxs-lookup"><span data-stu-id="38f1f-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38f1f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38f1f-111">Requirements</span></span>  
 <span data-ttu-id="38f1f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38f1f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38f1f-113">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="38f1f-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="38f1f-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38f1f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38f1f-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38f1f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f1f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="38f1f-116">See Also</span></span>  
 
