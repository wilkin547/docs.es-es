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
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727554"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="d762d-102">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="d762d-102">LoadStringRC Function</span></span>

<span data-ttu-id="d762d-103">Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d762d-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="d762d-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d762d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d762d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d762d-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d762d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d762d-106">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="d762d-107">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d762d-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d762d-108">enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.</span><span class="sxs-lookup"><span data-stu-id="d762d-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="d762d-109">de Tamaño del búfer del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d762d-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="d762d-110">de Tendrán.</span><span class="sxs-lookup"><span data-stu-id="d762d-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d762d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d762d-111">Return Value</span></span>  

 <span data-ttu-id="d762d-112">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d762d-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d762d-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="d762d-113">Return code</span></span>|<span data-ttu-id="d762d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d762d-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d762d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d762d-115">S_OK</span></span>|<span data-ttu-id="d762d-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d762d-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="d762d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d762d-117">E_INVALIDARG</span></span>|<span data-ttu-id="d762d-118">`szBuffer` es null o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="d762d-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d762d-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d762d-119">Remarks</span></span>  

 <span data-ttu-id="d762d-120">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d762d-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d762d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d762d-121">Requirements</span></span>  

 <span data-ttu-id="d762d-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d762d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d762d-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d762d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d762d-124">**Biblioteca:** MSCorEE.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="d762d-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d762d-125">Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d762d-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d762d-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d762d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d762d-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d762d-127">See also</span></span>

- [<span data-ttu-id="d762d-128">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="d762d-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="d762d-129">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d762d-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
