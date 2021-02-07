---
description: 'Más información acerca de: IMetaDataEmit::D método efineModuleRef'
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
ms.openlocfilehash: b5af5e458f749d2315612bbe9419f037331f8c46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753398"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="b9f0c-103">IMetaDataEmit::DefineModuleRef (Método)</span><span class="sxs-lookup"><span data-stu-id="b9f0c-103">IMetaDataEmit::DefineModuleRef Method</span></span>

<span data-ttu-id="b9f0c-104">Crea la firma de metadatos para un módulo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-104">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9f0c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9f0c-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="b9f0c-107">de Nombre del otro archivo de metadatos, normalmente un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-107">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="b9f0c-108">Este es el nombre de archivo únicamente.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-108">This is the file name only.</span></span> <span data-ttu-id="b9f0c-109">No use un nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-109">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="b9f0c-110">enuncia El `mdModuleRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-110">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f0c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9f0c-111">Requirements</span></span>  

 <span data-ttu-id="b9f0c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f0c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f0c-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9f0c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9f0c-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9f0c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9f0c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f0c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9f0c-116">See also</span></span>

- [<span data-ttu-id="b9f0c-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9f0c-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b9f0c-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9f0c-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
