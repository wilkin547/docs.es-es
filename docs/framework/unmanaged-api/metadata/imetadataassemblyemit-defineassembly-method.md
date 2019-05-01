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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b95a583aec87e3ba3e247d1ef800302b62657837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044829"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="661ae-102">IMetaDataAssemblyEmit::DefineAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="661ae-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="661ae-103">Crea un `Assembly` estructura que contienen metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="661ae-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="661ae-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="661ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="661ae-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="661ae-106">[in] La clave pública que identifica al publicador del ensamblado, o NULL si el ensamblado no tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="661ae-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="661ae-107">[in] El tamaño en bytes de `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="661ae-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="661ae-108">[in] El identificador del algoritmo hash se utiliza para cifrar los archivos en el ensamblado, o NULL para especificar el algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="661ae-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="661ae-109">[in] El nombre de texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="661ae-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="661ae-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="661ae-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="661ae-111">[in] Un puntero a una instancia ASSEMBLYMETADATA que contiene la información de versión, la plataforma y la configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="661ae-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="661ae-112">[in] Una combinación de [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores que describen las características del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="661ae-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="661ae-113">[out] Un puntero al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="661ae-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="661ae-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="661ae-114">Remarks</span></span>  
 <span data-ttu-id="661ae-115">Solo un `Assembly` estructura de los metadatos se puede definir dentro de un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="661ae-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661ae-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="661ae-116">Requirements</span></span>  
 <span data-ttu-id="661ae-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="661ae-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="661ae-118">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="661ae-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="661ae-119">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="661ae-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="661ae-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661ae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661ae-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="661ae-121">See also</span></span>

- [<span data-ttu-id="661ae-122">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="661ae-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
