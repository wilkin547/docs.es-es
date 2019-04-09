---
title: IMetaDataAssemblyImport::EnumExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c32dcfe5d00e1d35f7c63aa98a33d26f6b179c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152690"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="3b8a2-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="3b8a2-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="3b8a2-103">Enumera los tipos exportados hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b8a2-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b8a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b8a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3b8a2-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3b8a2-107">Esto debe ser un valor null valor cuando el `EnumExportedTypes` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="3b8a2-108">[out] La enumeración de `mdExportedType` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3b8a2-109">[in] El número máximo de `mdExportedType` tokens que se pueden colocar en el `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3b8a2-110">[out] El número de `mdExportedType` tokens realmente están colocan en `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b8a2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b8a2-111">Return Value</span></span>  
  
|<span data-ttu-id="3b8a2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b8a2-112">HRESULT</span></span>|<span data-ttu-id="3b8a2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b8a2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` <span data-ttu-id="3b8a2-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3b8a2-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3b8a2-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="3b8a2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b8a2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b8a2-117">Requirements</span></span>  
 <span data-ttu-id="3b8a2-118">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b8a2-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b8a2-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b8a2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b8a2-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b8a2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3b8a2-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b8a2-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b8a2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b8a2-122">See also</span></span>

- [<span data-ttu-id="3b8a2-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b8a2-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
