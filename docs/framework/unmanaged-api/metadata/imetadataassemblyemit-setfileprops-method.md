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
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431876"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="e332d-102">IMetaDataAssemblyEmit::SetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e332d-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="e332d-103">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="e332d-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e332d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e332d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e332d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e332d-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="e332d-106">de Símbolo (token) de metadatos que especifica el `File` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="e332d-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e332d-107">de Puntero a los datos hash asociados al archivo.</span><span class="sxs-lookup"><span data-stu-id="e332d-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e332d-108">de Tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="e332d-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="e332d-109">de Combinación bit a bit de valores de [CorFileFlags (](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) que especifican varios atributos del archivo.</span><span class="sxs-lookup"><span data-stu-id="e332d-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e332d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e332d-110">Remarks</span></span>  
 <span data-ttu-id="e332d-111">Para crear una estructura de metadatos de `File`, use el método [IMetaDataAssemblyEmit::D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e332d-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e332d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e332d-112">Requirements</span></span>  
 <span data-ttu-id="e332d-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e332d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e332d-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e332d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e332d-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e332d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e332d-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e332d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e332d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e332d-117">See also</span></span>

- [<span data-ttu-id="e332d-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e332d-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
