---
title: "IMetaDataAssemblyImport::FindManifestResourceByName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d6cc738c227157b45e242fb46a672d28d6ce778
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="a1661-102">IMetaDataAssemblyImport::FindManifestResourceByName (Método)</span><span class="sxs-lookup"><span data-stu-id="a1661-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="a1661-103">Obtiene un puntero al recurso de manifiesto con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="a1661-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1661-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1661-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1661-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1661-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a1661-106">[in] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="a1661-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="a1661-107">[out] La matriz que se utiliza para almacenar el `mdManifestResource` los tokens de metadatos, cada uno de los cuales representa un recurso del manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a1661-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1661-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1661-108">Remarks</span></span>  
 <span data-ttu-id="a1661-109">El `FindManifestResourceByName` método usa las reglas estándares empleadas por common language runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="a1661-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1661-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1661-110">Requirements</span></span>  
 <span data-ttu-id="a1661-111">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1661-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1661-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1661-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1661-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1661-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1661-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1661-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1661-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1661-115">See Also</span></span>  
 [<span data-ttu-id="a1661-116">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1661-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="a1661-117">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="a1661-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
