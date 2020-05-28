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
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008149"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="614dc-102">IMetaDataAssemblyEmit::DefineFile (Método)</span><span class="sxs-lookup"><span data-stu-id="614dc-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="614dc-103">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="614dc-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="614dc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="614dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="614dc-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="614dc-106">de Nombre del archivo que se va a consumir.</span><span class="sxs-lookup"><span data-stu-id="614dc-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="614dc-107">de Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="614dc-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="614dc-108">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="614dc-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="614dc-109">de Combinación bit a bit de `FileFlags` valores que especifican la configuración de propiedades.</span><span class="sxs-lookup"><span data-stu-id="614dc-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="614dc-110">enuncia Puntero al token devuelto `File` .</span><span class="sxs-lookup"><span data-stu-id="614dc-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="614dc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="614dc-111">Remarks</span></span>  
 <span data-ttu-id="614dc-112">Se `File` debe definir una estructura de metadatos para cada archivo que formaba parte de este ensamblado en el momento en que se compiló este ensamblado, excluyendo el archivo que contiene los metadatos.</span><span class="sxs-lookup"><span data-stu-id="614dc-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614dc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="614dc-113">Requirements</span></span>  
 <span data-ttu-id="614dc-114">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="614dc-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614dc-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="614dc-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="614dc-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="614dc-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="614dc-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="614dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614dc-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="614dc-118">See also</span></span>

- [<span data-ttu-id="614dc-119">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="614dc-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
