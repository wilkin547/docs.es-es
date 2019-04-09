---
title: IMetaDataAssemblyImport::FindManifestResourceByName (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf61da362251577acadb83915404eba7508b3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141575"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="16072-102">IMetaDataAssemblyImport::FindManifestResourceByName (Método)</span><span class="sxs-lookup"><span data-stu-id="16072-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="16072-103">Obtiene un puntero al recurso de manifiesto con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="16072-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16072-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16072-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="16072-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16072-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="16072-106">[in] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="16072-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="16072-107">[out] Matriz utilizada para almacenar el `mdManifestResource` los tokens de metadatos, cada uno de los cuales representa un recurso del manifiesto.</span><span class="sxs-lookup"><span data-stu-id="16072-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16072-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16072-108">Remarks</span></span>  
 <span data-ttu-id="16072-109">El `FindManifestResourceByName` método usa las reglas estándares empleadas por common language runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="16072-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16072-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16072-110">Requirements</span></span>  
 <span data-ttu-id="16072-111">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16072-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16072-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="16072-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16072-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16072-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="16072-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="16072-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16072-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="16072-115">See also</span></span>

- [<span data-ttu-id="16072-116">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16072-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="16072-117">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="16072-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
