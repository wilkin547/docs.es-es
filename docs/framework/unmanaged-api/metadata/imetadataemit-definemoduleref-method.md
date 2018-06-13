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
ms.openlocfilehash: 4503c3c745fde148c77ff30c9ece008dd9d54829
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445801"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="43ed6-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="43ed6-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="43ed6-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="43ed6-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ed6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43ed6-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43ed6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43ed6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="43ed6-106">[in] El nombre de otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="43ed6-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="43ed6-107">Esto es solo el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="43ed6-107">This is the file name only.</span></span> <span data-ttu-id="43ed6-108">No utilice un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="43ed6-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="43ed6-109">[out] Asignado `mdModuleRef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="43ed6-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43ed6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43ed6-110">Requirements</span></span>  
 <span data-ttu-id="43ed6-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43ed6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ed6-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43ed6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43ed6-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43ed6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43ed6-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43ed6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ed6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="43ed6-115">See Also</span></span>  
 [<span data-ttu-id="43ed6-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43ed6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="43ed6-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43ed6-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
