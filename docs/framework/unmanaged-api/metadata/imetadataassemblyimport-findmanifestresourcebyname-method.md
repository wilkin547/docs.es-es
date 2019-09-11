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
ms.openlocfilehash: aaaae5bda88d1fbc9949a080c5765127fd112bde
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855957"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="a9ac6-102">IMetaDataAssemblyImport::FindManifestResourceByName (Método)</span><span class="sxs-lookup"><span data-stu-id="a9ac6-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="a9ac6-103">Obtiene un puntero al recurso de manifiesto con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="a9ac6-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ac6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9ac6-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a9ac6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9ac6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a9ac6-106">de Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="a9ac6-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="a9ac6-107">enuncia Matriz que se usa para almacenar `mdManifestResource` los tokens de metadatos, cada uno de los cuales representa un recurso de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a9ac6-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9ac6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9ac6-108">Remarks</span></span>  
 <span data-ttu-id="a9ac6-109">El `FindManifestResourceByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="a9ac6-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ac6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9ac6-110">Requirements</span></span>  
 <span data-ttu-id="a9ac6-111">**Plataforma** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9ac6-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ac6-112">**Encabezado**: Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9ac6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9ac6-113">**Biblioteca** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9ac6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9ac6-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ac6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ac6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9ac6-115">See also</span></span>

- [<span data-ttu-id="a9ac6-116">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9ac6-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="a9ac6-117">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="a9ac6-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
