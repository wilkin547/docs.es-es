---
title: IMetaDataEmit::DefineModuleRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128822"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="d177c-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="d177c-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="d177c-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d177c-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d177c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d177c-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d177c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d177c-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d177c-106">[in] El nombre de otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="d177c-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="d177c-107">Esto es sólo el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d177c-107">This is the file name only.</span></span> <span data-ttu-id="d177c-108">No use un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="d177c-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="d177c-109">[out] Asignado `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="d177c-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d177c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d177c-110">Requirements</span></span>  
 <span data-ttu-id="d177c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d177c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d177c-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d177c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d177c-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d177c-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d177c-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d177c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d177c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d177c-115">See also</span></span>

- [<span data-ttu-id="d177c-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d177c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d177c-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d177c-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
