---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6667812ab7f9acff2a66e458f68d77a0d670bc2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446916"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="0d5e3-102">IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="0d5e3-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="0d5e3-103">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d5e3-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d5e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d5e3-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="0d5e3-106">[in] El token de metadatos que especifica el `AssemblyRef` estructura de metadatos que puede modificar.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="0d5e3-107">[in] La clave pública del publicador del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="0d5e3-108">[in] El tamaño en bytes de `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="0d5e3-109">[in] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="0d5e3-110">[in] Un puntero a una instancia ASSEMBLYMETADATA que contiene la información de versión, la plataforma y la configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0d5e3-111">[in] Un puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0d5e3-112">[in] El tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="0d5e3-113">[in] Una combinación bit a bit de [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valores que especifican los atributos del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d5e3-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d5e3-114">Remarks</span></span>  
 <span data-ttu-id="0d5e3-115">Para crear un `AssemblyRef` estructura de los metadatos, use la [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="0d5e3-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5e3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d5e3-116">Requirements</span></span>  
 <span data-ttu-id="0d5e3-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d5e3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5e3-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d5e3-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d5e3-119">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d5e3-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d5e3-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5e3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5e3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d5e3-121">See Also</span></span>  
 [<span data-ttu-id="0d5e3-122">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d5e3-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
