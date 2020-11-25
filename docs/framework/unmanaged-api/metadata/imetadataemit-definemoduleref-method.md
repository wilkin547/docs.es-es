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
ms.openlocfilehash: 96d24705d80dabcda691edec497a4a30b6d37dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719559"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="7e004-102">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="7e004-102">IMetaDataEmit::DefineModuleRef Method</span></span>

<span data-ttu-id="7e004-103">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7e004-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e004-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e004-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e004-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e004-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="7e004-106">de Nombre del otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="7e004-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="7e004-107">Este es el nombre de archivo únicamente.</span><span class="sxs-lookup"><span data-stu-id="7e004-107">This is the file name only.</span></span> <span data-ttu-id="7e004-108">No use un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="7e004-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="7e004-109">enuncia El `mdModuleRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="7e004-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e004-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e004-110">Requirements</span></span>  

 <span data-ttu-id="7e004-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e004-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e004-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e004-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e004-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e004-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e004-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e004-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e004-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e004-115">See also</span></span>

- [<span data-ttu-id="7e004-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e004-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7e004-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e004-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
