---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineFile'
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
ms.openlocfilehash: 825ef44c2b0a5f312b4c5f9c851d62e75709c7ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671058"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="e9739-103">IMetaDataAssemblyEmit::DefineFile (Método)</span><span class="sxs-lookup"><span data-stu-id="e9739-103">IMetaDataAssemblyEmit::DefineFile Method</span></span>

<span data-ttu-id="e9739-104">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="e9739-104">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9739-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9739-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9739-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9739-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="e9739-107">de Nombre del archivo que se va a consumir.</span><span class="sxs-lookup"><span data-stu-id="e9739-107">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e9739-108">de Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e9739-108">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e9739-109">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="e9739-109">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="e9739-110">de Combinación bit a bit de `FileFlags` valores que especifican la configuración de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9739-110">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="e9739-111">enuncia Puntero al token devuelto `File` .</span><span class="sxs-lookup"><span data-stu-id="e9739-111">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9739-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9739-112">Remarks</span></span>  

 <span data-ttu-id="e9739-113">Se `File` debe definir una estructura de metadatos para cada archivo que formaba parte de este ensamblado en el momento en que se compiló este ensamblado, excluyendo el archivo que contiene los metadatos.</span><span class="sxs-lookup"><span data-stu-id="e9739-113">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9739-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9739-114">Requirements</span></span>  

 <span data-ttu-id="e9739-115">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9739-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9739-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9739-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9739-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9739-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9739-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9739-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9739-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9739-119">See also</span></span>

- [<span data-ttu-id="e9739-120">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9739-120">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
