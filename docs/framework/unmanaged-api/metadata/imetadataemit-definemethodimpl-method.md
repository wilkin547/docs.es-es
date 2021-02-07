---
description: 'Más información acerca de: IMetaDataEmit::D método efineMethodImpl'
title: IMetaDataEmit::DefineMethodImpl (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 9c79d713e61bfcc7b3191e570ed727b128422bf1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753411"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="8c33e-103">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="8c33e-103">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="8c33e-104">Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token a esa definición de implementación de método.</span><span class="sxs-lookup"><span data-stu-id="8c33e-104">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c33e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c33e-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c33e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c33e-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="8c33e-107">de `mdTypedef` Token de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="8c33e-107">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="8c33e-108">de El `mdMethodDef` `mdMemberRef` token o del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="8c33e-108">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="8c33e-109">de El `mdMethodDef` `mdMemberRef` token o del método de interfaz que se implementa.</span><span class="sxs-lookup"><span data-stu-id="8c33e-109">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c33e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c33e-110">Requirements</span></span>  

 <span data-ttu-id="8c33e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c33e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c33e-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8c33e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c33e-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c33e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c33e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c33e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c33e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c33e-115">See also</span></span>

- [<span data-ttu-id="8c33e-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c33e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8c33e-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c33e-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
