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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116326"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="f591a-102">ICeeGen::TruncateSection (Método)</span><span class="sxs-lookup"><span data-stu-id="f591a-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="f591a-103">Trunca la sección de código especificado por la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="f591a-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="f591a-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="f591a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f591a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f591a-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f591a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f591a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="f591a-107">[in] Sección que se va a truncar.</span><span class="sxs-lookup"><span data-stu-id="f591a-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="f591a-108">[in] La longitud, en bytes, en la que se va a truncar la sección.</span><span class="sxs-lookup"><span data-stu-id="f591a-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f591a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f591a-109">Remarks</span></span>  
 <span data-ttu-id="f591a-110">Llamar a `TruncateSection` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="f591a-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f591a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f591a-111">Requirements</span></span>  
 <span data-ttu-id="f591a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f591a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f591a-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f591a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f591a-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f591a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f591a-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f591a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f591a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f591a-116">See also</span></span>

- [<span data-ttu-id="f591a-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f591a-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
