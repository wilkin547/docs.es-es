---
description: 'Más información acerca de: IValidator:: FormatEventInfo ((método)'
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
ms.openlocfilehash: 28ecf9ab2b14cd2fdd178a4ad9d8e218f7038a9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680166"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="bc474-103">IValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="bc474-103">IValidator::FormatEventInfo Method</span></span>

<span data-ttu-id="bc474-104">Obtiene el mensaje de error correspondiente al error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="bc474-104">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc474-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc474-105">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc474-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc474-106">Parameters</span></span>  

 `hVECode`  
 <span data-ttu-id="bc474-107">de Valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="bc474-107">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="bc474-108">de `VEContext` Instancia de que contiene información de contexto sobre el error de validación.</span><span class="sxs-lookup"><span data-stu-id="bc474-108">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="bc474-109">[in, out] Cadena que contiene el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="bc474-109">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="bc474-110">de La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="bc474-110">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="bc474-111">de Matriz segura que contiene los parámetros adicionales que describen el error.</span><span class="sxs-lookup"><span data-stu-id="bc474-111">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc474-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc474-112">Requirements</span></span>  

 <span data-ttu-id="bc474-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc474-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc474-114">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="bc474-114">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="bc474-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc474-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc474-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc474-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
