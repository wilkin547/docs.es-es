---
description: 'Más información acerca de: Loadstringrcex ((función)'
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
ms.openlocfilehash: d3fe4b97014e5093dd8d209a5e27bac4ed7b879f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679927"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="3be97-103">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="3be97-103">LoadStringRCEx Function</span></span>

<span data-ttu-id="3be97-104">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="3be97-104">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="3be97-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3be97-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be97-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3be97-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3be97-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3be97-107">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="3be97-108">de Identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3be97-108">[in] A culture identifier.</span></span> <span data-ttu-id="3be97-109">Pass-1 para `lcid` para utilizar la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3be97-109">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="3be97-110">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3be97-110">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="3be97-111">enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.</span><span class="sxs-lookup"><span data-stu-id="3be97-111">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="3be97-112">de Tamaño del búfer del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="3be97-112">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="3be97-113">de Tendrán.</span><span class="sxs-lookup"><span data-stu-id="3be97-113">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="3be97-114">enuncia Puntero a la longitud del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="3be97-114">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3be97-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3be97-115">Return Value</span></span>  

 <span data-ttu-id="3be97-116">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="3be97-116">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3be97-117">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="3be97-117">Return code</span></span>|<span data-ttu-id="3be97-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3be97-118">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3be97-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="3be97-119">S_OK</span></span>|<span data-ttu-id="3be97-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3be97-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="3be97-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3be97-121">E_INVALIDARG</span></span>|<span data-ttu-id="3be97-122">`szBuffer` es null, o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="3be97-122">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3be97-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3be97-123">Remarks</span></span>  

 <span data-ttu-id="3be97-124">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3be97-124">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be97-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3be97-125">Requirements</span></span>  

 <span data-ttu-id="3be97-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3be97-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be97-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3be97-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3be97-128">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3be97-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3be97-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be97-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be97-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3be97-130">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3be97-131">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="3be97-131">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="3be97-132">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3be97-132">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
