---
title: ICeeGen::AddSectionReloc (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c281d03c6e3774938cfa6e4b4b3a541738b38489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444348"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="bc4d7-102">ICeeGen::AddSectionReloc (Método)</span><span class="sxs-lookup"><span data-stu-id="bc4d7-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="bc4d7-103">Agrega una instrucción .reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="bc4d7-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc4d7-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc4d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc4d7-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="bc4d7-107">[in] La sección de código en memoria que se va a agregar una instrucción .reloc.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="bc4d7-108">[in] El desplazamiento de la sección.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="bc4d7-109">[in] La sección a la que `offset` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="bc4d7-110">[in] Uno de los [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) valores, que indica el tipo de instrucción .reloc para agregar.</span><span class="sxs-lookup"><span data-stu-id="bc4d7-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc4d7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc4d7-111">Requirements</span></span>  
 <span data-ttu-id="bc4d7-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc4d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc4d7-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc4d7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc4d7-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc4d7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc4d7-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4d7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc4d7-116">See Also</span></span>  
 [<span data-ttu-id="bc4d7-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc4d7-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
