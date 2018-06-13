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
ms.openlocfilehash: 1dccb2a3a3f3aaf0f209c8f3543056ab81c562dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443904"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="e7010-102">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="e7010-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="e7010-103">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="e7010-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="e7010-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e7010-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7010-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7010-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7010-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7010-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="e7010-107">[in] Cadena que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="e7010-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="e7010-108">[out] La dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="e7010-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7010-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7010-109">Requirements</span></span>  
 <span data-ttu-id="e7010-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7010-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7010-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7010-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7010-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7010-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7010-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7010-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7010-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7010-114">See Also</span></span>  
 [<span data-ttu-id="e7010-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7010-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
