---
title: "IMetaDataAssemblyEmit::SetAssemblyProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aab505700b669cae071420117abd71332f49d8b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="c6465-102">IMetaDataAssemblyEmit::SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c6465-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="c6465-103">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="c6465-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6465-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6465-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6465-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6465-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="c6465-106">[in] El token de metadatos que especifica el `Assembly` estructura de metadatos que puede modificar.</span><span class="sxs-lookup"><span data-stu-id="c6465-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="c6465-107">[in] Un puntero a la clave pública del publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6465-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="c6465-108">[in] El tamaño en bytes de `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="c6465-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="c6465-109">[in] El identificador para el algoritmo hash utilizado para resumir los archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6465-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="c6465-110">[in] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6465-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="c6465-111">[in] Un puntero a la ASSEMBLYMETADATA que contiene información de versión, la plataforma y la configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6465-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="c6465-112">[in] Una combinación bit a bit de [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valores que especifican distintos atributos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6465-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6465-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6465-113">Remarks</span></span>  
 <span data-ttu-id="c6465-114">Para crear un `Assembly` estructura de los metadatos, use la [IMetaDataAssemblyEmit:: DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c6465-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6465-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6465-115">Requirements</span></span>  
 <span data-ttu-id="c6465-116">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6465-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6465-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6465-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6465-118">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6465-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6465-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6465-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6465-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6465-120">See Also</span></span>  
 [<span data-ttu-id="c6465-121">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6465-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
