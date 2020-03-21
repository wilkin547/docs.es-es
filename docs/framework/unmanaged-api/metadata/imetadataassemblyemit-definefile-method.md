---
title: IMetaDataAssemblyEmit::DefineFile (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176063"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="ac9ed-102">IMetaDataAssemblyEmit::DefineFile (Método)</span><span class="sxs-lookup"><span data-stu-id="ac9ed-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="ac9ed-103">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac9ed-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac9ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac9ed-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ac9ed-106">[en] El nombre del archivo que se va a consumir.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ac9ed-107">[en] Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ac9ed-108">[en] El tamaño en `pbHashValue`bytes de .</span><span class="sxs-lookup"><span data-stu-id="ac9ed-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="ac9ed-109">[en] Una combinación `FileFlags` bit a bit de valores que especifican la configuración de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="ac9ed-110">[fuera] Un puntero al `File` token devuelto.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9ed-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ac9ed-111">Remarks</span></span>  
 <span data-ttu-id="ac9ed-112">Se `File` debe definir una estructura de metadatos para cada archivo que formaba parte de este ensamblado en el momento en que se creó este ensamblado, excluyendo el archivo que contiene los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ac9ed-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9ed-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac9ed-113">Requirements</span></span>  
 <span data-ttu-id="ac9ed-114">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9ed-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9ed-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac9ed-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac9ed-116">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac9ed-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac9ed-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9ed-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac9ed-118">See also</span></span>

- [<span data-ttu-id="ac9ed-119">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac9ed-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
