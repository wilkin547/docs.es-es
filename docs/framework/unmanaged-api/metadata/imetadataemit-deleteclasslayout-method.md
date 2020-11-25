---
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
ms.openlocfilehash: d355e0e3b2461932384ca11d83d46fd1dc63b80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732689"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="a9147-102">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="a9147-102">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="a9147-103">Destruye la firma de metadatos de diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="a9147-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9147-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9147-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9147-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9147-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="a9147-106">de `mdTypeDef` Token de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="a9147-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9147-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9147-107">Requirements</span></span>  

 <span data-ttu-id="a9147-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9147-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9147-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9147-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9147-110">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9147-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9147-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9147-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9147-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9147-112">See also</span></span>

- [<span data-ttu-id="a9147-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9147-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a9147-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9147-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
