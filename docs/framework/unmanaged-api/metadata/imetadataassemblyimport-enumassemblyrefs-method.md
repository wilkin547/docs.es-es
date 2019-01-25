---
title: IMetaDataAssemblyImport::EnumAssemblyRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d10fb391953e924feb553ae4516fb7674345ed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592021"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="598c7-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="598c7-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="598c7-103">Enumera la `mdAssemblyRef` instancias que se definen en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="598c7-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="598c7-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="598c7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="598c7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="598c7-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="598c7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="598c7-107">Esto debe ser un valor null valor cuando el `EnumAssemblyRefs` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="598c7-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="598c7-108">[out] La enumeración de `mdAssemblyRef` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="598c7-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="598c7-109">[in] El número máximo de tokens que se pueden colocar en el `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="598c7-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="598c7-110">[out] El número de tokens se realizó en `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="598c7-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598c7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="598c7-111">Return Value</span></span>  
  
|<span data-ttu-id="598c7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="598c7-112">HRESULT</span></span>|<span data-ttu-id="598c7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="598c7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="598c7-114">`EnumAssemblyRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="598c7-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="598c7-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="598c7-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="598c7-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="598c7-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="598c7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="598c7-117">Requirements</span></span>  
 <span data-ttu-id="598c7-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="598c7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="598c7-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="598c7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="598c7-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="598c7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="598c7-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="598c7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598c7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="598c7-122">See also</span></span>
- [<span data-ttu-id="598c7-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="598c7-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
