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
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727541"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="4e310-102">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="4e310-102">LoadStringRCEx Function</span></span>

<span data-ttu-id="4e310-103">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="4e310-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="4e310-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4e310-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e310-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e310-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4e310-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e310-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="4e310-107">de Identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="4e310-107">[in] A culture identifier.</span></span> <span data-ttu-id="4e310-108">Pass-1 para `lcid` para utilizar la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4e310-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="4e310-109">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4e310-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="4e310-110">enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.</span><span class="sxs-lookup"><span data-stu-id="4e310-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="4e310-111">de Tamaño del búfer del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4e310-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="4e310-112">de Tendrán.</span><span class="sxs-lookup"><span data-stu-id="4e310-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="4e310-113">enuncia Puntero a la longitud del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4e310-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e310-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e310-114">Return Value</span></span>  

 <span data-ttu-id="4e310-115">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e310-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4e310-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="4e310-116">Return code</span></span>|<span data-ttu-id="4e310-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e310-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4e310-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e310-118">S_OK</span></span>|<span data-ttu-id="4e310-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e310-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="4e310-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4e310-120">E_INVALIDARG</span></span>|<span data-ttu-id="4e310-121">`szBuffer` es null, o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="4e310-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e310-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e310-122">Remarks</span></span>  

 <span data-ttu-id="4e310-123">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="4e310-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e310-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e310-124">Requirements</span></span>  

 <span data-ttu-id="4e310-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e310-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e310-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e310-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e310-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e310-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e310-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e310-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e310-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e310-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4e310-130">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="4e310-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="4e310-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="4e310-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
