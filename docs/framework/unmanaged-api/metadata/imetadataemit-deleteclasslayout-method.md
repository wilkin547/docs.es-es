---
description: 'Más información acerca de: IMetaDataEmit::D método eleteClassLayout'
title: IMetaDataEmit::DeleteClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: 44be89f415087a1457a83bb1167e1017d26ed5ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783994"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="74205-103">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="74205-103">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="74205-104">Destruye la firma de metadatos de diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="74205-104">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74205-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74205-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74205-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74205-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="74205-107">de `mdTypeDef` Token de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="74205-107">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74205-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74205-108">Requirements</span></span>  

 <span data-ttu-id="74205-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74205-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74205-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74205-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74205-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74205-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74205-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74205-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74205-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="74205-113">See also</span></span>

- [<span data-ttu-id="74205-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74205-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="74205-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74205-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
