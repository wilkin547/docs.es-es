---
title: LoadStringRC (Función)
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e020b65966dc03bf326220ab0bab26bc61155c0c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485491"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="af673-102">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="af673-102">LoadStringRC Function</span></span>
<span data-ttu-id="af673-103">Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="af673-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="af673-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af673-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af673-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af673-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af673-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af673-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="af673-107">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="af673-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="af673-108">[out] Un búfer que contiene el mensaje de error tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="af673-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="af673-109">[in] El tamaño del búfer de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="af673-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="af673-110">[in] Pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="af673-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af673-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af673-111">Return Value</span></span>  
 <span data-ttu-id="af673-112">Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="af673-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="af673-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="af673-113">Return code</span></span>|<span data-ttu-id="af673-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="af673-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="af673-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="af673-115">S_OK</span></span>|<span data-ttu-id="af673-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="af673-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="af673-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="af673-117">E_INVALIDARG</span></span>|<span data-ttu-id="af673-118">`szBuffer` es null o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="af673-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af673-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af673-119">Remarks</span></span>  
 <span data-ttu-id="af673-120">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="af673-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af673-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af673-121">Requirements</span></span>  
 <span data-ttu-id="af673-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af673-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af673-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af673-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af673-124">**Biblioteca:** MSCorEE.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="af673-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="af673-125">Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af673-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="af673-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af673-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af673-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="af673-127">See also</span></span>
- [<span data-ttu-id="af673-128">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="af673-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="af673-129">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="af673-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
