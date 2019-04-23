---
title: IMetaDataAssemblyEmit::SetExportedTypeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c09140488730179616d11932faa3542f704958a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123752"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="b5710-102">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b5710-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="b5710-103">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="b5710-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5710-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5710-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5710-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5710-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="b5710-106">[in] El token de metadatos que especifica el `ExportedType` estructura de metadatos que se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="b5710-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="b5710-107">[in] El token de tipo `File`, `AssemblyRef`, o `ExportedType`, que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="b5710-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="b5710-108">[in] El `TypeDef` token al que hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="b5710-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="b5710-109">[in] Una combinación bit a bit de valores que especifican los atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="b5710-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5710-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5710-110">Remarks</span></span>  
 <span data-ttu-id="b5710-111">Para crear un `ExportedType` estructura de los metadatos, use el [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b5710-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5710-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5710-112">Requirements</span></span>  
 <span data-ttu-id="b5710-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5710-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5710-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5710-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5710-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5710-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5710-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5710-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5710-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5710-117">See also</span></span>

- [<span data-ttu-id="b5710-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5710-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
