---
title: "IMetaDataEmit::DefineModuleRef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineModuleRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b3131e6cebf09b0767d1331656ff16b2b55d749
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="41e7a-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="41e7a-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="41e7a-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="41e7a-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41e7a-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41e7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41e7a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="41e7a-106">[in] El nombre de otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="41e7a-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="41e7a-107">Esto es solo el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="41e7a-107">This is the file name only.</span></span> <span data-ttu-id="41e7a-108">No utilice un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="41e7a-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="41e7a-109">[out] Asignado `mdModuleRef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="41e7a-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41e7a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41e7a-110">Requirements</span></span>  
 <span data-ttu-id="41e7a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41e7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e7a-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41e7a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41e7a-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41e7a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41e7a-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41e7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e7a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="41e7a-115">See Also</span></span>  
 [<span data-ttu-id="41e7a-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41e7a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="41e7a-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41e7a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
