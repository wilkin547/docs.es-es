---
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
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175842"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="96e20-102">IMetaDataEmit::DefineMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="96e20-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="96e20-103">Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token a esa definición de referencia.</span><span class="sxs-lookup"><span data-stu-id="96e20-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96e20-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96e20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96e20-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="96e20-106">[en] Token para la clase o interfaz del miembro de destino, si el miembro no es global; si el miembro es `mdModuleRef` global, el token para ese otro archivo.</span><span class="sxs-lookup"><span data-stu-id="96e20-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="96e20-107">[en] El nombre del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="96e20-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="96e20-108">[en] La firma del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="96e20-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="96e20-109">[en] El recuento de `pvSigBlob`bytes en .</span><span class="sxs-lookup"><span data-stu-id="96e20-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="96e20-110">[fuera] El `mdMemberRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="96e20-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e20-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96e20-111">Requirements</span></span>  
 <span data-ttu-id="96e20-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e20-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e20-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96e20-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96e20-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96e20-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96e20-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e20-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e20-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96e20-116">See also</span></span>

- [<span data-ttu-id="96e20-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96e20-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="96e20-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96e20-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
