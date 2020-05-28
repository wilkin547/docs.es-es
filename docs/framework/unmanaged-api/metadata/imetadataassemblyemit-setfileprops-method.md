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
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008071"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="2fcf1-102">IMetaDataAssemblyEmit::SetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="2fcf1-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="2fcf1-103">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="2fcf1-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fcf1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fcf1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fcf1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fcf1-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="2fcf1-106">de Token de metadatos que especifica la `File` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="2fcf1-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2fcf1-107">de Puntero a los datos hash asociados al archivo.</span><span class="sxs-lookup"><span data-stu-id="2fcf1-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2fcf1-108">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="2fcf1-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="2fcf1-109">de Combinación bit a bit de valores de [CorFileFlags (](corfileflags-enumeration.md) que especifican varios atributos del archivo.</span><span class="sxs-lookup"><span data-stu-id="2fcf1-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fcf1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fcf1-110">Remarks</span></span>  
 <span data-ttu-id="2fcf1-111">Para crear una `File` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2fcf1-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fcf1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fcf1-112">Requirements</span></span>  
 <span data-ttu-id="2fcf1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fcf1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fcf1-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2fcf1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fcf1-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2fcf1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fcf1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fcf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fcf1-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fcf1-117">See also</span></span>

- [<span data-ttu-id="2fcf1-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fcf1-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
