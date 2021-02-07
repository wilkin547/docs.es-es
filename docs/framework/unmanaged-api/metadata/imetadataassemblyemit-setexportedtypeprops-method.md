---
description: 'Más información acerca de: IMetaDataAssemblyEmit:: Setexportedtypeprops ((método)'
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
ms.openlocfilehash: 61032abd7b049af29c583e9aee126184af3c78f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678125"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="e15b0-103">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e15b0-103">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>

<span data-ttu-id="e15b0-104">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="e15b0-104">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e15b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e15b0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e15b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e15b0-106">Parameters</span></span>  

 `ct`  
 <span data-ttu-id="e15b0-107">de Token de metadatos que especifica la `ExportedType` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="e15b0-107">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="e15b0-108">de El token, de tipo `File` , `AssemblyRef` o `ExportedType` , que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="e15b0-108">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="e15b0-109">de `TypeDef` Token al que se hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="e15b0-109">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="e15b0-110">de Combinación bit a bit de valores que especifican atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="e15b0-110">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e15b0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e15b0-111">Remarks</span></span>  

 <span data-ttu-id="e15b0-112">Para crear una `ExportedType` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e15b0-112">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e15b0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e15b0-113">Requirements</span></span>  

 <span data-ttu-id="e15b0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e15b0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e15b0-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e15b0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e15b0-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e15b0-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e15b0-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e15b0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15b0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e15b0-118">See also</span></span>

- [<span data-ttu-id="e15b0-119">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e15b0-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
