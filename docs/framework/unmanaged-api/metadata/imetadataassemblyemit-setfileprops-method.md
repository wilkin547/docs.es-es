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
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176037"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="26110-102">IMetaDataAssemblyEmit::SetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="26110-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="26110-103">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="26110-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26110-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26110-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26110-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26110-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="26110-106">[en] El token de metadatos `File` que especifica la estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="26110-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="26110-107">[en] Puntero a los datos hash asociados al archivo.</span><span class="sxs-lookup"><span data-stu-id="26110-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="26110-108">[en] El tamaño en `pbHashValue`bytes de .</span><span class="sxs-lookup"><span data-stu-id="26110-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="26110-109">[en] Combinación bit a bit de [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valores que especifican varios atributos del archivo.</span><span class="sxs-lookup"><span data-stu-id="26110-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26110-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26110-110">Remarks</span></span>  
 <span data-ttu-id="26110-111">Para crear `File` una estructura de metadatos, utilice el [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="26110-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26110-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26110-112">Requirements</span></span>  
 <span data-ttu-id="26110-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26110-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26110-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26110-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26110-115">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26110-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26110-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26110-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26110-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26110-117">See also</span></span>

- [<span data-ttu-id="26110-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26110-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
