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
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209962"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="122cf-102">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="122cf-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="122cf-103">Emite la cadena especificada en la base de código.</span><span class="sxs-lookup"><span data-stu-id="122cf-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="122cf-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="122cf-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="122cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="122cf-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="122cf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="122cf-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="122cf-107">[in] Cadena que se emita.</span><span class="sxs-lookup"><span data-stu-id="122cf-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="122cf-108">[out] La dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="122cf-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="122cf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="122cf-109">Requirements</span></span>  
 <span data-ttu-id="122cf-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="122cf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="122cf-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="122cf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="122cf-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="122cf-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="122cf-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="122cf-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="122cf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="122cf-114">See also</span></span>

- [<span data-ttu-id="122cf-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="122cf-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
