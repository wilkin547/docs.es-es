---
description: 'Más información acerca de: Loadstringrc ((función)'
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
ms.openlocfilehash: 188597f9dc21b6a67fb84e91cd66b50ba5a514f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679930"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="bd437-103">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="bd437-103">LoadStringRC Function</span></span>

<span data-ttu-id="bd437-104">Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="bd437-104">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="bd437-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bd437-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd437-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd437-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd437-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd437-107">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="bd437-108">[in] HRESULT.</span><span class="sxs-lookup"><span data-stu-id="bd437-108">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="bd437-109">enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.</span><span class="sxs-lookup"><span data-stu-id="bd437-109">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="bd437-110">de Tamaño del búfer del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="bd437-110">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="bd437-111">de Tendrán.</span><span class="sxs-lookup"><span data-stu-id="bd437-111">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd437-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd437-112">Return Value</span></span>  

 <span data-ttu-id="bd437-113">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="bd437-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="bd437-114">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="bd437-114">Return code</span></span>|<span data-ttu-id="bd437-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd437-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="bd437-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd437-116">S_OK</span></span>|<span data-ttu-id="bd437-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd437-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="bd437-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bd437-118">E_INVALIDARG</span></span>|<span data-ttu-id="bd437-119">`szBuffer` es null o `iMax` es cero (0).</span><span class="sxs-lookup"><span data-stu-id="bd437-119">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd437-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd437-120">Remarks</span></span>  

 <span data-ttu-id="bd437-121">Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="bd437-121">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd437-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd437-122">Requirements</span></span>  

 <span data-ttu-id="bd437-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd437-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd437-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bd437-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd437-125">**Biblioteca:** MSCorEE.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="bd437-125">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="bd437-126">Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd437-126">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="bd437-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd437-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd437-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd437-128">See also</span></span>

- [<span data-ttu-id="bd437-129">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="bd437-129">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="bd437-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="bd437-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
