---
title: IMetaDataAssemblyEmit::SetFileProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044751"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="72f9c-102">IMetaDataAssemblyEmit::SetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="72f9c-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="72f9c-103">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="72f9c-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72f9c-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f9c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72f9c-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="72f9c-106">[in] El token de metadatos que especifica el `File` estructura de metadatos que se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="72f9c-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="72f9c-107">[in] Un puntero a los hash de los datos asociados con el archivo.</span><span class="sxs-lookup"><span data-stu-id="72f9c-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="72f9c-108">[in] El tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="72f9c-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="72f9c-109">[in] Una combinación bit a bit de [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valores que especifican distintos atributos del archivo.</span><span class="sxs-lookup"><span data-stu-id="72f9c-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72f9c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72f9c-110">Remarks</span></span>  
 <span data-ttu-id="72f9c-111">Para crear un `File` estructura de los metadatos, use el [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="72f9c-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f9c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72f9c-112">Requirements</span></span>  
 <span data-ttu-id="72f9c-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72f9c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f9c-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="72f9c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72f9c-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72f9c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72f9c-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f9c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f9c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="72f9c-117">See also</span></span>

- [<span data-ttu-id="72f9c-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72f9c-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
