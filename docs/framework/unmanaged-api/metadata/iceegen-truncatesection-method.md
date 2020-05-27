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
ms.openlocfilehash: 387f5f01f2d2589c0b34e50b69398e1feb0e77e0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008253"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="b8786-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="b8786-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="b8786-103">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="b8786-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="b8786-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="b8786-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8786-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8786-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8786-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8786-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b8786-107">de La sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="b8786-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="b8786-108">de Longitud, en bytes, por la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="b8786-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8786-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8786-109">Remarks</span></span>  
 <span data-ttu-id="b8786-110">Llame `TruncateSection` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="b8786-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8786-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8786-111">Requirements</span></span>  
 <span data-ttu-id="b8786-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8786-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8786-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b8786-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8786-114">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8786-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8786-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8786-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8786-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8786-116">See also</span></span>

- [<span data-ttu-id="b8786-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8786-117">ICeeGen Interface</span></span>](iceegen-interface.md)
