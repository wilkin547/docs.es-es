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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176050"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="f19a4-102">IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f19a4-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="f19a4-103">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="f19a4-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f19a4-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f19a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f19a4-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="f19a4-106">[en] El token de metadatos `AssemblyRef` que especifica la estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="f19a4-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="f19a4-107">[en] La clave pública del publicador del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f19a4-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="f19a4-108">[en] El tamaño en `pbPublicKeyOrToken`bytes de .</span><span class="sxs-lookup"><span data-stu-id="f19a4-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="f19a4-109">[en] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f19a4-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f19a4-110">[en] Puntero a una instancia de ASSEMBLYMETADATA que contiene la información de versión, plataforma y configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f19a4-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f19a4-111">[en] Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f19a4-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f19a4-112">[en] El tamaño en `pbHashValue`bytes de .</span><span class="sxs-lookup"><span data-stu-id="f19a4-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="f19a4-113">[en] Combinación bit a bit de [assemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valores que especifican atributos del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f19a4-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f19a4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f19a4-114">Remarks</span></span>  
 <span data-ttu-id="f19a4-115">Para crear `AssemblyRef` una estructura de metadatos, utilice el [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f19a4-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19a4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f19a4-116">Requirements</span></span>  
 <span data-ttu-id="f19a4-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f19a4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19a4-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f19a4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f19a4-119">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f19a4-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f19a4-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19a4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19a4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f19a4-121">See also</span></span>

- [<span data-ttu-id="f19a4-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f19a4-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
