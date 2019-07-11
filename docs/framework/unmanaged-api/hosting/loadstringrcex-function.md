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
ms.openlocfilehash: 4a0cac77d7bf7611acf6042298bfe6814d8f4352
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768449"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="d876b-102">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="d876b-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="d876b-103">Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="d876b-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="d876b-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d876b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d876b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d876b-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d876b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d876b-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="d876b-107">[in] Un identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="d876b-107">[in] A culture identifier.</span></span> <span data-ttu-id="d876b-108">Se pasa -1 `lcid` para usar la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d876b-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="d876b-109">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d876b-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d876b-110">[out] Un búfer que contiene el mensaje de error tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="d876b-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="d876b-111">[in] El tamaño del búfer de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d876b-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="d876b-112">[in] Pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="d876b-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="d876b-113">[out] Un puntero a la longitud del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d876b-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d876b-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d876b-114">Return Value</span></span>  
 <span data-ttu-id="d876b-115">Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d876b-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d876b-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="d876b-116">Return code</span></span>|<span data-ttu-id="d876b-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d876b-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d876b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d876b-118">S_OK</span></span>|<span data-ttu-id="d876b-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d876b-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="d876b-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d876b-120">E_INVALIDARG</span></span>|<span data-ttu-id="d876b-121">`szBuffer` es null, o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="d876b-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d876b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d876b-122">Remarks</span></span>  
 <span data-ttu-id="d876b-123">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d876b-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d876b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d876b-124">Requirements</span></span>  
 <span data-ttu-id="d876b-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d876b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d876b-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d876b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d876b-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d876b-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d876b-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d876b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d876b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d876b-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d876b-130">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="d876b-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="d876b-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d876b-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
