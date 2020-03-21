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
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177736"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="8aadf-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="8aadf-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="8aadf-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8aadf-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aadf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8aadf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aadf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8aadf-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8aadf-106">[en] El nombre del otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="8aadf-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="8aadf-107">Este es el nombre de archivo solamente.</span><span class="sxs-lookup"><span data-stu-id="8aadf-107">This is the file name only.</span></span> <span data-ttu-id="8aadf-108">No utilice un nombre de ruta de acceso completo.</span><span class="sxs-lookup"><span data-stu-id="8aadf-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="8aadf-109">[fuera] El `mdModuleRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="8aadf-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aadf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8aadf-110">Requirements</span></span>  
 <span data-ttu-id="8aadf-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aadf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aadf-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8aadf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8aadf-113">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8aadf-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8aadf-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aadf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aadf-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8aadf-115">See also</span></span>

- [<span data-ttu-id="8aadf-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8aadf-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8aadf-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8aadf-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
