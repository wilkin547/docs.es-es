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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5d386b1d3f95e703cc5d9ad1353ea6b84b5b455
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176051"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="54130-102">IMetaDataEmit::DefineMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="54130-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="54130-103">Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.</span><span class="sxs-lookup"><span data-stu-id="54130-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54130-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54130-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54130-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54130-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="54130-106">[in] Token para el miembro de destino clase o interfaz, si el miembro no es global; Si el miembro es global, la `mdModuleRef` token para ese otro archivo.</span><span class="sxs-lookup"><span data-stu-id="54130-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="54130-107">[in] El nombre del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="54130-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="54130-108">[in] La firma del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="54130-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="54130-109">[in] El recuento de bytes en `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="54130-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="54130-110">[out] El `mdMemberRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="54130-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54130-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54130-111">Requirements</span></span>  
 <span data-ttu-id="54130-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54130-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54130-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="54130-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54130-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54130-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54130-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54130-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54130-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="54130-116">See also</span></span>

- [<span data-ttu-id="54130-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54130-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="54130-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54130-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
