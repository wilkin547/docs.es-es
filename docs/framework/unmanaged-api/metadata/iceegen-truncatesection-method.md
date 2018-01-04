---
title: "ICeeGen::TruncateSection (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.TruncateSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="e4202-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="e4202-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="e4202-103">Trunca la sección de código especificado por la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="e4202-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="e4202-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e4202-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4202-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4202-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4202-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4202-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e4202-107">[in] Sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="e4202-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="e4202-108">[in] La longitud, en bytes, en la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="e4202-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4202-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4202-109">Remarks</span></span>  
 <span data-ttu-id="e4202-110">Llame a `TruncateSection` sólo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="e4202-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4202-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4202-111">Requirements</span></span>  
 <span data-ttu-id="e4202-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4202-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4202-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e4202-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4202-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4202-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4202-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4202-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4202-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4202-116">See Also</span></span>  
 [<span data-ttu-id="e4202-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4202-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
