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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176245"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="9cece-102">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="9cece-102">LoadStringRC Function</span></span>
<span data-ttu-id="9cece-103">Traduce un valor HRESULT en un mensaje de error mediante la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9cece-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="9cece-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9cece-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cece-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cece-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cece-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cece-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="9cece-107">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="9cece-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="9cece-108">[fuera] Un búfer que contiene el mensaje de error al completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="9cece-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="9cece-109">[en] El tamaño del búfer de mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="9cece-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="9cece-110">[en] Ignorado.</span><span class="sxs-lookup"><span data-stu-id="9cece-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cece-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9cece-111">Return Value</span></span>  
 <span data-ttu-id="9cece-112">Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="9cece-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="9cece-113">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="9cece-113">Return code</span></span>|<span data-ttu-id="9cece-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cece-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9cece-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cece-115">S_OK</span></span>|<span data-ttu-id="9cece-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9cece-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="9cece-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9cece-117">E_INVALIDARG</span></span>|<span data-ttu-id="9cece-118">`szBuffer`es nulo `iMax` o es cero (0).</span><span class="sxs-lookup"><span data-stu-id="9cece-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cece-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9cece-119">Remarks</span></span>  
 <span data-ttu-id="9cece-120">Si el método no se `szBuffer` completa correctamente, contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="9cece-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cece-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cece-121">Requirements</span></span>  
 <span data-ttu-id="9cece-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cece-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cece-123">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="9cece-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cece-124">**Biblioteca:** MSCorEE.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="9cece-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="9cece-125">Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9cece-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9cece-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cece-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cece-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cece-127">See also</span></span>

- [<span data-ttu-id="9cece-128">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="9cece-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="9cece-129">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9cece-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
