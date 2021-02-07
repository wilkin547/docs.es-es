---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineAssembly'
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
ms.openlocfilehash: cd53a4398f49ca96072fc5f5b6dcac35a94bdc59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706765"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="653fb-103">IMetaDataAssemblyEmit::DefineAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="653fb-103">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>

<span data-ttu-id="653fb-104">Crea una `Assembly` estructura que contiene metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="653fb-104">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="653fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="653fb-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="653fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="653fb-106">Parameters</span></span>  

 `pbPublicKey`  
 <span data-ttu-id="653fb-107">de La clave pública que identifica al publicador del ensamblado, o NULL si el ensamblado no tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="653fb-107">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="653fb-108">de Tamaño en bytes de `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="653fb-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="653fb-109">de Identificador del algoritmo hash que se va a utilizar para cifrar los archivos del ensamblado, o NULL para especificar el algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="653fb-109">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="653fb-110">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="653fb-110">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="653fb-111">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="653fb-111">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="653fb-112">de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="653fb-112">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="653fb-113">de Combinación de valores [corassemblyflags (](corassemblyflags-enumeration.md) que describen las características del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="653fb-113">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="653fb-114">enuncia Puntero al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="653fb-114">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="653fb-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="653fb-115">Remarks</span></span>  

 <span data-ttu-id="653fb-116">Solo `Assembly` se puede definir una estructura de metadatos dentro de un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="653fb-116">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="653fb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="653fb-117">Requirements</span></span>  

 <span data-ttu-id="653fb-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="653fb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="653fb-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="653fb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="653fb-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="653fb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="653fb-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="653fb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653fb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="653fb-122">See also</span></span>

- [<span data-ttu-id="653fb-123">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="653fb-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
