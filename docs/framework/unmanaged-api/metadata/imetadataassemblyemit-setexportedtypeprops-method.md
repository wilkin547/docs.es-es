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
ms.openlocfilehash: ae682c354a7a5188611b103008a3e18f8d821260
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431941"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="5c3f5-102">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5c3f5-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="5c3f5-103">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="5c3f5-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c3f5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c3f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c3f5-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="5c3f5-106">de Símbolo (token) de metadatos que especifica el `ExportedType` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="5c3f5-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5c3f5-107">de El token, de tipo `File`, `AssemblyRef`o `ExportedType`, que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="5c3f5-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="5c3f5-108">de El token de `TypeDef` al que se hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="5c3f5-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="5c3f5-109">de Combinación bit a bit de valores que especifican atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="5c3f5-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c3f5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c3f5-110">Remarks</span></span>  
 <span data-ttu-id="5c3f5-111">Para crear una estructura de metadatos de `ExportedType`, use el método [IMetaDataAssemblyEmit::D efineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c3f5-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c3f5-112">Requirements</span></span>  
 <span data-ttu-id="5c3f5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c3f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3f5-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c3f5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c3f5-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c3f5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c3f5-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3f5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3f5-117">See also</span></span>

- [<span data-ttu-id="5c3f5-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3f5-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
