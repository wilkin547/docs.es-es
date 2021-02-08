---
description: 'Más información acerca de: IMetaDataAssemblyEmit:: SetFileProps ((método)'
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
ms.openlocfilehash: 482aa11b85eaf05d126c4fcc0d5a1aced85002d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789312"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="9daae-103">IMetaDataAssemblyEmit::SetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="9daae-103">IMetaDataAssemblyEmit::SetFileProps Method</span></span>

<span data-ttu-id="9daae-104">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="9daae-104">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9daae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9daae-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9daae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9daae-106">Parameters</span></span>  

 `file`  
 <span data-ttu-id="9daae-107">de Token de metadatos que especifica la `File` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="9daae-107">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="9daae-108">de Puntero a los datos hash asociados al archivo.</span><span class="sxs-lookup"><span data-stu-id="9daae-108">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="9daae-109">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="9daae-109">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="9daae-110">de Combinación bit a bit de valores de [CorFileFlags (](corfileflags-enumeration.md) que especifican varios atributos del archivo.</span><span class="sxs-lookup"><span data-stu-id="9daae-110">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9daae-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9daae-111">Remarks</span></span>  

 <span data-ttu-id="9daae-112">Para crear una `File` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9daae-112">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9daae-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9daae-113">Requirements</span></span>  

 <span data-ttu-id="9daae-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9daae-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9daae-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9daae-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9daae-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9daae-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9daae-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9daae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9daae-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9daae-118">See also</span></span>

- [<span data-ttu-id="9daae-119">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9daae-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
