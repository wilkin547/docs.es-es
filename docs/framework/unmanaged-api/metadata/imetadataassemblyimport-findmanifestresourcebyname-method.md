---
description: 'Más información sobre: IMetaDataAssemblyImport:: Findmanifestresourcebyname ((método)'
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
ms.openlocfilehash: 1d1312277675a1f2bf213221ab8d9d2a584733a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784176"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="3e2e9-103">IMetaDataAssemblyImport::FindManifestResourceByName (Método)</span><span class="sxs-lookup"><span data-stu-id="3e2e9-103">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>

<span data-ttu-id="3e2e9-104">Obtiene un puntero al recurso de manifiesto con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3e2e9-104">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e2e9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e2e9-105">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="3e2e9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e2e9-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="3e2e9-107">[in] Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="3e2e9-107">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="3e2e9-108">enuncia Matriz que se usa para almacenar los `mdManifestResource` tokens de metadatos, cada uno de los cuales representa un recurso de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="3e2e9-108">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e2e9-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3e2e9-109">Remarks</span></span>  

 <span data-ttu-id="3e2e9-110">El `FindManifestResourceByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="3e2e9-110">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e2e9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e2e9-111">Requirements</span></span>  

 <span data-ttu-id="3e2e9-112">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e2e9-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e2e9-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e2e9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e2e9-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e2e9-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e2e9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e2e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e2e9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e2e9-116">See also</span></span>

- [<span data-ttu-id="3e2e9-117">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e2e9-117">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="3e2e9-118">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3e2e9-118">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
