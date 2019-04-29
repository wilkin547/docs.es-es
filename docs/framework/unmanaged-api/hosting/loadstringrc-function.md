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
ms.openlocfilehash: f17ecfe683de0739e4e1e063d38836eecf949336
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765315"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="f9150-102">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="f9150-102">LoadStringRC Function</span></span>
<span data-ttu-id="f9150-103">Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f9150-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="f9150-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9150-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9150-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9150-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9150-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9150-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="f9150-107">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="f9150-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="f9150-108">[out] Un búfer que contiene el mensaje de error tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9150-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="f9150-109">[in] El tamaño del búfer de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f9150-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="f9150-110">[in] Pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="f9150-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9150-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f9150-111">Return Value</span></span>  
 <span data-ttu-id="f9150-112">Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9150-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f9150-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="f9150-113">Return code</span></span>|<span data-ttu-id="f9150-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9150-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f9150-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9150-115">S_OK</span></span>|<span data-ttu-id="f9150-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9150-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f9150-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f9150-117">E_INVALIDARG</span></span>|<span data-ttu-id="f9150-118">`szBuffer` es null o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="f9150-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9150-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9150-119">Remarks</span></span>  
 <span data-ttu-id="f9150-120">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f9150-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9150-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9150-121">Requirements</span></span>  
 <span data-ttu-id="f9150-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9150-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9150-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9150-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9150-124">**Biblioteca:** MSCorEE.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="f9150-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="f9150-125">Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9150-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="f9150-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9150-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9150-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9150-127">See also</span></span>

- [<span data-ttu-id="f9150-128">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="f9150-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="f9150-129">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f9150-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
