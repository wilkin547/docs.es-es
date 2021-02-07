---
description: 'Más información sobre: IMetaDataAssemblyImport:: Enumfiles ((método)'
title: IMetaDataAssemblyImport::EnumFiles (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 25282edd081e937e4c84334f9f004e201b9db46f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671027"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="e9d0d-103">IMetaDataAssemblyImport::EnumFiles (Método)</span><span class="sxs-lookup"><span data-stu-id="e9d0d-103">IMetaDataAssemblyImport::EnumFiles Method</span></span>

<span data-ttu-id="e9d0d-104">Enumera los archivos a los que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-104">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d0d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9d0d-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d0d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9d0d-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e9d0d-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e9d0d-108">Debe ser un valor null para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-108">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="e9d0d-109">enuncia Matriz utilizada para almacenar los `mdFile` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-109">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e9d0d-110">de Número máximo de `mdFile` tokens que se pueden colocar en `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="e9d0d-110">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e9d0d-111">enuncia Número de `mdFile` tokens realmente colocados en `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="e9d0d-111">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9d0d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9d0d-112">Return Value</span></span>  
  
|<span data-ttu-id="e9d0d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9d0d-113">HRESULT</span></span>|<span data-ttu-id="e9d0d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9d0d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e9d0d-115">`EnumFiles` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-115">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e9d0d-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="e9d0d-117">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="e9d0d-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9d0d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9d0d-118">Requirements</span></span>  

 <span data-ttu-id="e9d0d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d0d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d0d-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9d0d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9d0d-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9d0d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d0d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d0d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d0d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9d0d-123">See also</span></span>

- [<span data-ttu-id="e9d0d-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9d0d-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
