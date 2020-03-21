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
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177851"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="d2d4a-102">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d2d4a-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="d2d4a-103">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d4a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2d4a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2d4a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2d4a-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="d2d4a-106">[en] El token de metadatos `ExportedType` que especifica la estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d2d4a-107">[en] El token, `File`de `AssemblyRef`tipo `ExportedType`, , o , que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="d2d4a-108">[en] El `TypeDef` token al que se hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="d2d4a-109">[en] Una combinación bit a bit de valores que especifican atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2d4a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d2d4a-110">Remarks</span></span>  
 <span data-ttu-id="d2d4a-111">Para crear `ExportedType` una estructura de metadatos, utilice el [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d2d4a-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2d4a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2d4a-112">Requirements</span></span>  
 <span data-ttu-id="d2d4a-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2d4a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2d4a-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2d4a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2d4a-115">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2d4a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2d4a-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2d4a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d4a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2d4a-117">See also</span></span>

- [<span data-ttu-id="d2d4a-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2d4a-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
