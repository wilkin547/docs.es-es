---
title: ICeeGen::TruncateSection (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 3005db62bba4089c669a00f62e3c1e62f9e1dae9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685713"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="d11b2-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="d11b2-102">ICeeGen::TruncateSection Method</span></span>

<span data-ttu-id="d11b2-103">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="d11b2-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="d11b2-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="d11b2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11b2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d11b2-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11b2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d11b2-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="d11b2-107">de La sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="d11b2-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="d11b2-108">de Longitud, en bytes, por la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="d11b2-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d11b2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d11b2-109">Remarks</span></span>  

 <span data-ttu-id="d11b2-110">Llame `TruncateSection` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="d11b2-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d11b2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d11b2-111">Requirements</span></span>  

 <span data-ttu-id="d11b2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11b2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d11b2-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d11b2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d11b2-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d11b2-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d11b2-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11b2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d11b2-116">See also</span></span>

- [<span data-ttu-id="d11b2-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d11b2-117">ICeeGen Interface</span></span>](iceegen-interface.md)
