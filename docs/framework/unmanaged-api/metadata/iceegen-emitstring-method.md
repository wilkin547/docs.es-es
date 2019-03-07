---
title: ICeeGen::EmitString (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63ddd3b5cc79cedba6d6acc6a9b6b70c00d917fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476235"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="c043c-102">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="c043c-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="c043c-103">Emite la cadena especificada en la base de código.</span><span class="sxs-lookup"><span data-stu-id="c043c-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="c043c-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="c043c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c043c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c043c-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c043c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c043c-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="c043c-107">[in] Cadena que se emita.</span><span class="sxs-lookup"><span data-stu-id="c043c-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="c043c-108">[out] La dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="c043c-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c043c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c043c-109">Requirements</span></span>  
 <span data-ttu-id="c043c-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c043c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c043c-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c043c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c043c-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c043c-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c043c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c043c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c043c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c043c-114">See also</span></span>
- [<span data-ttu-id="c043c-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c043c-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
