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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177980"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="61d64-102">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="61d64-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="61d64-103">Traduce un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="61d64-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="61d64-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="61d64-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d64-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61d64-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61d64-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61d64-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="61d64-107">[en] Identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="61d64-107">[in] A culture identifier.</span></span> <span data-ttu-id="61d64-108">Pase -1 `lcid` para usar la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="61d64-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="61d64-109">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="61d64-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="61d64-110">[fuera] Un búfer que contiene el mensaje de error al completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="61d64-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="61d64-111">[en] El tamaño del búfer de mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="61d64-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="61d64-112">[en] Ignorado.</span><span class="sxs-lookup"><span data-stu-id="61d64-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="61d64-113">[fuera] Un puntero a la longitud del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="61d64-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61d64-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="61d64-114">Return Value</span></span>  
 <span data-ttu-id="61d64-115">Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="61d64-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="61d64-116">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="61d64-116">Return code</span></span>|<span data-ttu-id="61d64-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="61d64-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="61d64-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="61d64-118">S_OK</span></span>|<span data-ttu-id="61d64-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="61d64-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="61d64-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61d64-120">E_INVALIDARG</span></span>|<span data-ttu-id="61d64-121">`szBuffer`es nulo, `iMax` o es cero (0).</span><span class="sxs-lookup"><span data-stu-id="61d64-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d64-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61d64-122">Remarks</span></span>  
 <span data-ttu-id="61d64-123">Si el método no se `szBuffer` completa correctamente, contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="61d64-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61d64-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61d64-124">Requirements</span></span>  
 <span data-ttu-id="61d64-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61d64-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61d64-126">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="61d64-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61d64-127">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="61d64-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61d64-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61d64-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d64-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61d64-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="61d64-130">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="61d64-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="61d64-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="61d64-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
