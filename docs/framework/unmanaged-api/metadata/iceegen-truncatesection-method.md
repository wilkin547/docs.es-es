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
ms.openlocfilehash: 87a70587027f283ef5976089b3f2daf1204e68ec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426131"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="906ad-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="906ad-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="906ad-103">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="906ad-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="906ad-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="906ad-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="906ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="906ad-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="906ad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="906ad-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="906ad-107">de La sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="906ad-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="906ad-108">de Longitud, en bytes, por la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="906ad-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="906ad-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="906ad-109">Remarks</span></span>  
 <span data-ttu-id="906ad-110">Llame solo a `TruncateSection` si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="906ad-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="906ad-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="906ad-111">Requirements</span></span>  
 <span data-ttu-id="906ad-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="906ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="906ad-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="906ad-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="906ad-114">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="906ad-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="906ad-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="906ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906ad-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="906ad-116">See also</span></span>

- [<span data-ttu-id="906ad-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="906ad-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
