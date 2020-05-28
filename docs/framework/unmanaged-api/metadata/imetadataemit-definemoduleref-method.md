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
ms.openlocfilehash: efff491d92ac7910f43f76965ef98d1d0e4ba0aa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004444"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="83108-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="83108-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="83108-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="83108-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83108-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83108-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83108-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83108-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="83108-106">de Nombre del otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="83108-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="83108-107">Este es el nombre de archivo únicamente.</span><span class="sxs-lookup"><span data-stu-id="83108-107">This is the file name only.</span></span> <span data-ttu-id="83108-108">No use un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="83108-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="83108-109">enuncia El `mdModuleRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="83108-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83108-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83108-110">Requirements</span></span>  
 <span data-ttu-id="83108-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83108-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83108-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83108-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83108-113">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83108-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83108-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83108-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83108-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83108-115">See also</span></span>

- [<span data-ttu-id="83108-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83108-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="83108-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83108-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
