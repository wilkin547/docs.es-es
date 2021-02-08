---
description: 'Más información sobre: ICeeGen:: Truncatesection ((método)'
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
ms.openlocfilehash: 074c7d7b4222b5b22f1d9b79169d531cd5544b1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784215"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="42e75-103">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="42e75-103">ICeeGen::TruncateSection Method</span></span>

<span data-ttu-id="42e75-104">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="42e75-104">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="42e75-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="42e75-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e75-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42e75-106">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e75-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42e75-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="42e75-108">de La sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="42e75-108">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="42e75-109">de Longitud, en bytes, por la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="42e75-109">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e75-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42e75-110">Remarks</span></span>  

 <span data-ttu-id="42e75-111">Llame `TruncateSection` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="42e75-111">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e75-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42e75-112">Requirements</span></span>  

 <span data-ttu-id="42e75-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e75-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e75-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="42e75-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42e75-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42e75-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42e75-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e75-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e75-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="42e75-117">See also</span></span>

- [<span data-ttu-id="42e75-118">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42e75-118">ICeeGen Interface</span></span>](iceegen-interface.md)
