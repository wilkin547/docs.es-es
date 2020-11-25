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
ms.openlocfilehash: 076d027945dc27942e4b0989e14e86d829f76679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713496"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="fa416-102">IMetaDataAssemblyEmit::SetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="fa416-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>

<span data-ttu-id="fa416-103">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="fa416-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa416-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa416-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa416-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa416-105">Parameters</span></span>  

 `ct`  
 <span data-ttu-id="fa416-106">de Token de metadatos que especifica la `ExportedType` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="fa416-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="fa416-107">de El token, de tipo `File` , `AssemblyRef` o `ExportedType` , que especifica cómo se implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="fa416-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="fa416-108">de `TypeDef` Token al que se hace referencia en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="fa416-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="fa416-109">de Combinación bit a bit de valores que especifican atributos del tipo.</span><span class="sxs-lookup"><span data-stu-id="fa416-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa416-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa416-110">Remarks</span></span>  

 <span data-ttu-id="fa416-111">Para crear una `ExportedType` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fa416-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa416-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa416-112">Requirements</span></span>  

 <span data-ttu-id="fa416-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa416-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa416-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa416-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa416-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa416-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa416-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa416-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa416-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa416-117">See also</span></span>

- [<span data-ttu-id="fa416-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa416-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
