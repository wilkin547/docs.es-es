---
title: IMetaDataImport::EnumMemberRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: 68cdefe7ab362b26bbf060fa46766068eb0d7094
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503762"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="5ca6a-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="5ca6a-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="5ca6a-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ca6a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ca6a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5ca6a-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="5ca6a-107">de Un token TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="5ca6a-108">enuncia Matriz utilizada para almacenar los tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ca6a-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5ca6a-110">enuncia Número real de tokens de MemberRef devueltos en `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="5ca6a-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ca6a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5ca6a-111">Return Value</span></span>  
  
|<span data-ttu-id="5ca6a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ca6a-112">HRESULT</span></span>|<span data-ttu-id="5ca6a-113">Description</span><span class="sxs-lookup"><span data-stu-id="5ca6a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5ca6a-114">`EnumMemberRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5ca6a-115">No hay tokens de MemberRef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="5ca6a-116">En ese caso, `pcTokens` es a cero.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ca6a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ca6a-117">Requirements</span></span>  
 <span data-ttu-id="5ca6a-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ca6a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca6a-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5ca6a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ca6a-120">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5ca6a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ca6a-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca6a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca6a-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5ca6a-122">See also</span></span>

- [<span data-ttu-id="5ca6a-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ca6a-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5ca6a-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ca6a-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
