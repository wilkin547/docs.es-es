---
title: LoadStringRCEx (Función)
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 697557463aa949036acb21e63b9a82b1fb84b415
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105500"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="903dc-102">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="903dc-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="903dc-103">Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="903dc-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="903dc-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="903dc-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="903dc-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="903dc-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="903dc-107">[in] Un identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="903dc-107">[in] A culture identifier.</span></span> <span data-ttu-id="903dc-108">Se pasa -1 `lcid` para usar la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="903dc-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="903dc-109">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="903dc-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="903dc-110">[out] Un búfer que contiene el mensaje de error tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="903dc-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="903dc-111">[in] El tamaño del búfer de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="903dc-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="903dc-112">[in] Pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="903dc-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="903dc-113">[out] Un puntero a la longitud del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="903dc-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="903dc-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="903dc-114">Return Value</span></span>  
 <span data-ttu-id="903dc-115">Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="903dc-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="903dc-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="903dc-116">Return code</span></span>|<span data-ttu-id="903dc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="903dc-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="903dc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="903dc-118">S_OK</span></span>|<span data-ttu-id="903dc-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="903dc-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="903dc-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="903dc-120">E_INVALIDARG</span></span>|`szBuffer` <span data-ttu-id="903dc-121">es null, o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="903dc-121">is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="903dc-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="903dc-122">Remarks</span></span>  
 <span data-ttu-id="903dc-123">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="903dc-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903dc-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="903dc-124">Requirements</span></span>  
 <span data-ttu-id="903dc-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903dc-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903dc-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="903dc-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="903dc-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="903dc-127">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="903dc-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="903dc-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="903dc-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="903dc-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="903dc-130">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="903dc-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="903dc-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="903dc-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
