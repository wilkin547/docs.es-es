---
title: "IMetaDataAssemblyImport::FindExportedTypeByName (Método)"
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
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 010e6c29541e4b55353db4359c018935c5e1ef2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="62ce1-102">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="62ce1-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="62ce1-103">Obtiene un puntero a un tipo exportado, dados su nombre y el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="62ce1-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62ce1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ce1-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62ce1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62ce1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="62ce1-106">[in] El nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="62ce1-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="62ce1-107">[in] El token de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="62ce1-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="62ce1-108">Este valor es `mdExportedTypeNil` si exportado solicitado tipo no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="62ce1-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="62ce1-109">[out] Un puntero a la `mdExportedType` símbolo (token) que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="62ce1-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62ce1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62ce1-110">Remarks</span></span>  
 <span data-ttu-id="62ce1-111">El `FindExportedTypeByName` método usa las reglas estándares empleadas por common language runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="62ce1-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ce1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62ce1-112">Requirements</span></span>  
 <span data-ttu-id="62ce1-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ce1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ce1-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="62ce1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62ce1-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62ce1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62ce1-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ce1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ce1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="62ce1-117">See Also</span></span>  
 [<span data-ttu-id="62ce1-118">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62ce1-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="62ce1-119">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="62ce1-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
