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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1036d6080bf17eea288724c7980ce53dfa2121f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116326"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="e58d8-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="e58d8-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="e58d8-103">Trunca la sección de código especificado por la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="e58d8-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="e58d8-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e58d8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e58d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e58d8-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e58d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e58d8-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e58d8-107">[in] Sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="e58d8-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="e58d8-108">[in] La longitud, en bytes, en la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="e58d8-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e58d8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e58d8-109">Remarks</span></span>  
 <span data-ttu-id="e58d8-110">Llamar a `TruncateSection` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="e58d8-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e58d8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e58d8-111">Requirements</span></span>  
 <span data-ttu-id="e58d8-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e58d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e58d8-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e58d8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e58d8-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e58d8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e58d8-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e58d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58d8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e58d8-116">See also</span></span>

- [<span data-ttu-id="e58d8-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e58d8-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
