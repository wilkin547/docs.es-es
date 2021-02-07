---
description: 'Más información acerca de: IMetaDataEmit::D método efineMemberRef'
title: IMetaDataEmit::DefineMemberRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 1d88294cea14369c8a8f16b6048f96472fbb9502
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753424"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="aa104-103">IMetaDataEmit::DefineMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="aa104-103">IMetaDataEmit::DefineMemberRef Method</span></span>

<span data-ttu-id="aa104-104">Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.</span><span class="sxs-lookup"><span data-stu-id="aa104-104">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa104-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa104-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa104-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa104-106">Parameters</span></span>  

 `tkImport`  
 <span data-ttu-id="aa104-107">de Token de la clase o interfaz del miembro de destino, si el miembro no es global; Si el miembro es global, el `mdModuleRef` token del otro archivo.</span><span class="sxs-lookup"><span data-stu-id="aa104-107">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="aa104-108">de Nombre del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="aa104-108">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="aa104-109">de Firma del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="aa104-109">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="aa104-110">de Recuento de bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="aa104-110">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="aa104-111">enuncia El `mdMemberRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="aa104-111">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa104-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa104-112">Requirements</span></span>  

 <span data-ttu-id="aa104-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa104-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa104-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aa104-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa104-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa104-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa104-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa104-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa104-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa104-117">See also</span></span>

- [<span data-ttu-id="aa104-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa104-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="aa104-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa104-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
