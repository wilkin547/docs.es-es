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
ms.openlocfilehash: 576f4561ed782f091840ac378831110a1bfef9c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004704"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="15682-102">IMetaDataEmit::DefineMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="15682-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="15682-103">Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.</span><span class="sxs-lookup"><span data-stu-id="15682-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15682-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15682-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15682-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15682-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="15682-106">de Token de la clase o interfaz del miembro de destino, si el miembro no es global; Si el miembro es global, el `mdModuleRef` token del otro archivo.</span><span class="sxs-lookup"><span data-stu-id="15682-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="15682-107">de Nombre del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="15682-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="15682-108">de Firma del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="15682-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="15682-109">de Recuento de bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="15682-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="15682-110">enuncia El `mdMemberRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="15682-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15682-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15682-111">Requirements</span></span>  
 <span data-ttu-id="15682-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15682-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15682-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="15682-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15682-114">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="15682-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15682-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15682-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15682-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15682-116">See also</span></span>

- [<span data-ttu-id="15682-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15682-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="15682-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15682-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
