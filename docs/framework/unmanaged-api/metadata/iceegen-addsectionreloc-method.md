---
description: 'Más información sobre: ICeeGen:: AddSectionReloc ((método)'
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
ms.openlocfilehash: 715c506f0bdcb3fcef33b3e9165d1f9ae47c6073
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707181"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="22904-103">ICeeGen::AddSectionReloc (Método)</span><span class="sxs-lookup"><span data-stu-id="22904-103">ICeeGen::AddSectionReloc Method</span></span>

<span data-ttu-id="22904-104">Agrega una instrucción. reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="22904-104">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="22904-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="22904-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22904-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22904-106">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22904-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22904-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="22904-108">de La sección de código en memoria a la que se va a agregar una instrucción. reloc.</span><span class="sxs-lookup"><span data-stu-id="22904-108">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="22904-109">de Desplazamiento de la sección.</span><span class="sxs-lookup"><span data-stu-id="22904-109">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="22904-110">de La sección a la que `offset` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="22904-110">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="22904-111">de Uno de los valores de [ceesectionreloctype (](ceesectionreloctype-enumeration.md) , que indica el tipo de instrucción. reloc que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="22904-111">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22904-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22904-112">Requirements</span></span>  

 <span data-ttu-id="22904-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22904-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22904-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22904-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22904-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22904-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22904-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22904-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22904-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="22904-117">See also</span></span>

- [<span data-ttu-id="22904-118">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22904-118">ICeeGen Interface</span></span>](iceegen-interface.md)
