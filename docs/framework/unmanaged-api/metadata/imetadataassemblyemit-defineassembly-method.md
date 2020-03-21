---
title: IMetaDataAssemblyEmit::DefineAssembly (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177887"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="52a4e-102">IMetaDataAssemblyEmit::DefineAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="52a4e-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="52a4e-103">Crea `Assembly` una estructura que contiene metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="52a4e-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a4e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52a4e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52a4e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52a4e-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="52a4e-106">[en] La clave pública que identifica el publicador del ensamblado, o NULL si el ensamblado no tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="52a4e-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="52a4e-107">[en] El tamaño en `pbPublicKey`bytes de .</span><span class="sxs-lookup"><span data-stu-id="52a4e-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="52a4e-108">[en] Identificador del algoritmo hash que se va a usar para cifrar los archivos del ensamblado o NULL para especificar el algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="52a4e-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="52a4e-109">[en] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52a4e-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="52a4e-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="52a4e-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="52a4e-111">[en] Puntero a una instancia de ASSEMBLYMETADATA que contiene la información de versión, plataforma y configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52a4e-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="52a4e-112">[en] Combinación de [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores que describen las características del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52a4e-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="52a4e-113">[fuera] Un puntero al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="52a4e-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52a4e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52a4e-114">Remarks</span></span>  
 <span data-ttu-id="52a4e-115">Solo `Assembly` se puede definir una estructura de metadatos dentro de un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="52a4e-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a4e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52a4e-116">Requirements</span></span>  
 <span data-ttu-id="52a4e-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a4e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a4e-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52a4e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52a4e-119">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52a4e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52a4e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a4e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a4e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52a4e-121">See also</span></span>

- [<span data-ttu-id="52a4e-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52a4e-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
