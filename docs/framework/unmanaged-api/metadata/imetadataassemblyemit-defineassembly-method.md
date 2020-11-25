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
ms.openlocfilehash: 6d783e27c60db7381025f3b2382728e3996323ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725734"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="b151a-102">IMetaDataAssemblyEmit::DefineAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="b151a-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>

<span data-ttu-id="b151a-103">Crea una `Assembly` estructura que contiene metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b151a-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b151a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b151a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b151a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b151a-105">Parameters</span></span>  

 `pbPublicKey`  
 <span data-ttu-id="b151a-106">de La clave pública que identifica al publicador del ensamblado, o NULL si el ensamblado no tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="b151a-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="b151a-107">de Tamaño en bytes de `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="b151a-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="b151a-108">de Identificador del algoritmo hash que se va a utilizar para cifrar los archivos del ensamblado, o NULL para especificar el algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="b151a-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="b151a-109">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b151a-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="b151a-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b151a-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="b151a-111">de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b151a-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="b151a-112">de Combinación de valores [corassemblyflags (](corassemblyflags-enumeration.md) que describen las características del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b151a-112">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="b151a-113">enuncia Puntero al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b151a-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b151a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b151a-114">Remarks</span></span>  

 <span data-ttu-id="b151a-115">Solo `Assembly` se puede definir una estructura de metadatos dentro de un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b151a-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b151a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b151a-116">Requirements</span></span>  

 <span data-ttu-id="b151a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b151a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b151a-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b151a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b151a-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b151a-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b151a-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b151a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b151a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b151a-121">See also</span></span>

- [<span data-ttu-id="b151a-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b151a-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
