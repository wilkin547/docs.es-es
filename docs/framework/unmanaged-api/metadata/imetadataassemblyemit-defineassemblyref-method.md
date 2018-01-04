---
title: "IMetaDataAssemblyEmit::DefineAssemblyRef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 123bd37d189477eade72e3b0e74f923fecce57a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="33886-102">IMetaDataAssemblyEmit::DefineAssemblyRef (Método)</span><span class="sxs-lookup"><span data-stu-id="33886-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="33886-103">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="33886-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33886-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33886-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33886-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33886-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="33886-106">[in] La clave pública del publicador del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="33886-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="33886-107">La función auxiliar [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) puede utilizarse para obtener el hash de la clave pública que se pasará como parámetro.</span><span class="sxs-lookup"><span data-stu-id="33886-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="33886-108">[in] El tamaño en bytes de `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="33886-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="33886-109">[in] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="33886-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="33886-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="33886-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="33886-111">[in] Una instancia ASSEMBLYMETADATA que contiene la información de versión, la plataforma y la configuración regional del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="33886-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="33886-112">[in] Los datos hash asociados al ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="33886-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="33886-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="33886-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="33886-114">[in] El tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="33886-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="33886-115">[in] Una combinación bit a bit de [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores que influyen en el comportamiento del motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33886-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="33886-116">[out] Un puntero para el valor devuelto `AssemblyRef` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="33886-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33886-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33886-117">Remarks</span></span>  
 <span data-ttu-id="33886-118">Una `AssemblyRef` se debe definir la estructura de metadatos para cada ensamblado al que hace referencia a este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="33886-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="33886-119">En tiempo de ejecución, los detalles de un ensamblado de referencia se pasan a la resolución de ensamblado con un valor que indica que representan la información "como"compilada".</span><span class="sxs-lookup"><span data-stu-id="33886-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="33886-120">La resolución de ensamblado, a continuación, aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="33886-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33886-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33886-121">Requirements</span></span>  
 <span data-ttu-id="33886-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33886-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33886-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33886-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33886-124">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33886-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33886-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33886-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33886-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="33886-126">See Also</span></span>  
 [<span data-ttu-id="33886-127">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33886-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
