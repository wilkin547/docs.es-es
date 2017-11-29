---
title: "IMetaDataAssemblyEmit::DefineFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineFile
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3be44603eb16c6e74b34c0f569fc5bb11264ca0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="26e29-102">IMetaDataAssemblyEmit::DefineFile (Método)</span><span class="sxs-lookup"><span data-stu-id="26e29-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="26e29-103">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="26e29-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e29-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26e29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26e29-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="26e29-106">[in] El nombre del archivo que vayan a usar.</span><span class="sxs-lookup"><span data-stu-id="26e29-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="26e29-107">[in] Un puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26e29-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="26e29-108">[in] El tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="26e29-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="26e29-109">[in] Una combinación bit a bit de `FileFlags` valores que especifican los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="26e29-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="26e29-110">[out] Un puntero para el valor devuelto `File` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="26e29-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26e29-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26e29-111">Remarks</span></span>  
 <span data-ttu-id="26e29-112">Una `File` estructura de metadatos debe definirse para cada archivo que formaba parte de este ensamblado en el momento en que se compiló este ensamblado, sin incluir el archivo que contiene los metadatos.</span><span class="sxs-lookup"><span data-stu-id="26e29-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e29-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e29-113">Requirements</span></span>  
 <span data-ttu-id="26e29-114">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e29-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e29-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26e29-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26e29-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26e29-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26e29-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e29-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e29-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e29-118">See Also</span></span>  
 [<span data-ttu-id="26e29-119">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26e29-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
