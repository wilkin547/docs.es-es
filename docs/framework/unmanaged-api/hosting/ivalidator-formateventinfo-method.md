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
ms.openlocfilehash: 0c60631b5e034bc46d74412440d35d526359d043
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008578"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="fbb05-102">IValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="fbb05-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="fbb05-103">Obtiene el mensaje de error correspondiente al error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="fbb05-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbb05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbb05-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbb05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbb05-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="fbb05-106">de Valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="fbb05-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="fbb05-107">de `VEContext`Instancia de que contiene información de contexto sobre el error de validación.</span><span class="sxs-lookup"><span data-stu-id="fbb05-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="fbb05-108">[in, out] Cadena que contiene el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="fbb05-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="fbb05-109">de La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="fbb05-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="fbb05-110">de Matriz segura que contiene los parámetros adicionales que describen el error.</span><span class="sxs-lookup"><span data-stu-id="fbb05-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbb05-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbb05-111">Requirements</span></span>  
 <span data-ttu-id="fbb05-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbb05-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbb05-113">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="fbb05-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="fbb05-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fbb05-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbb05-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbb05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
