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
ms.openlocfilehash: 87a5224247c2d94613de482fbaa34bf978198bf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715542"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="0121d-102">ICeeGen::AddSectionReloc (Método)</span><span class="sxs-lookup"><span data-stu-id="0121d-102">ICeeGen::AddSectionReloc Method</span></span>

<span data-ttu-id="0121d-103">Agrega una instrucción. reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="0121d-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="0121d-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="0121d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0121d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0121d-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0121d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0121d-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="0121d-107">de La sección de código en memoria a la que se va a agregar una instrucción. reloc.</span><span class="sxs-lookup"><span data-stu-id="0121d-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="0121d-108">de Desplazamiento de la sección.</span><span class="sxs-lookup"><span data-stu-id="0121d-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="0121d-109">de La sección a la que `offset` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0121d-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="0121d-110">de Uno de los valores de [ceesectionreloctype (](ceesectionreloctype-enumeration.md) , que indica el tipo de instrucción. reloc que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="0121d-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0121d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0121d-111">Requirements</span></span>  

 <span data-ttu-id="0121d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0121d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0121d-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0121d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0121d-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0121d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0121d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0121d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0121d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0121d-116">See also</span></span>

- [<span data-ttu-id="0121d-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0121d-117">ICeeGen Interface</span></span>](iceegen-interface.md)
