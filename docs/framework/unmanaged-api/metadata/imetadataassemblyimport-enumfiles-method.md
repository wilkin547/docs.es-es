---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2ab06419491093a2de41d2ef25d16c01c03ebaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905338"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="f5253-102">IMetaDataAssemblyImport::EnumFiles (Método)</span><span class="sxs-lookup"><span data-stu-id="f5253-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="f5253-103">Enumera los archivos que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="f5253-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5253-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5253-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5253-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5253-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f5253-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="f5253-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f5253-107">Debe ser un valor null para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="f5253-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="f5253-108">[out] Matriz utilizada para almacenar el `mdFile` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f5253-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f5253-109">[in] El número máximo de `mdFile` tokens que se pueden colocar en `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="f5253-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f5253-110">[out] El número de `mdFile` tokens realmente están colocan en `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="f5253-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5253-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5253-111">Return Value</span></span>  
  
|<span data-ttu-id="f5253-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5253-112">HRESULT</span></span>|<span data-ttu-id="f5253-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5253-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f5253-114">`EnumFiles` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5253-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f5253-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="f5253-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f5253-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="f5253-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5253-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5253-117">Requirements</span></span>  
 <span data-ttu-id="f5253-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5253-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5253-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5253-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5253-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5253-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5253-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5253-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5253-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5253-122">See also</span></span>

- [<span data-ttu-id="f5253-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5253-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
