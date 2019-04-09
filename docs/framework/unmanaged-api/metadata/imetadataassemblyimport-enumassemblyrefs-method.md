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
ms.openlocfilehash: 91e253669b9f51e7c1d600ba11f13a9ce67fb58a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072485"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="2d131-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="2d131-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="2d131-103">Enumera la `mdAssemblyRef` instancias que se definen en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2d131-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d131-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d131-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d131-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d131-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2d131-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="2d131-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2d131-107">Esto debe ser un valor null valor cuando el `EnumAssemblyRefs` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="2d131-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="2d131-108">[out] La enumeración de `mdAssemblyRef` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2d131-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2d131-109">[in] El número máximo de tokens que se pueden colocar en el `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="2d131-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2d131-110">[out] El número de tokens se realizó en `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="2d131-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d131-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d131-111">Return Value</span></span>  
  
|<span data-ttu-id="2d131-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d131-112">HRESULT</span></span>|<span data-ttu-id="2d131-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d131-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` <span data-ttu-id="2d131-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d131-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2d131-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="2d131-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2d131-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="2d131-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d131-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d131-117">Requirements</span></span>  
 <span data-ttu-id="2d131-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d131-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d131-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="2d131-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d131-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d131-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2d131-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2d131-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d131-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d131-122">See also</span></span>

- [<span data-ttu-id="2d131-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d131-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
