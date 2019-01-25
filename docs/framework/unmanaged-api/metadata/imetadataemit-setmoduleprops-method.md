---
title: IMetaDataEmit::SetModuleProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86cb99023c0abfc70d292427b14986dbcea1d333
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586168"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="5ec8a-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5ec8a-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="5ec8a-103">Actualiza las referencias a un módulo definido por una llamada anterior a [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="5ec8a-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ec8a-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ec8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ec8a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5ec8a-106">[in] El nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="5ec8a-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="5ec8a-107">Esto es sólo el nombre de archivo y no el nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="5ec8a-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec8a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ec8a-108">Requirements</span></span>  
 <span data-ttu-id="5ec8a-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ec8a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ec8a-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ec8a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ec8a-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ec8a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ec8a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ec8a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec8a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ec8a-113">See also</span></span>
- [<span data-ttu-id="5ec8a-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ec8a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5ec8a-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ec8a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
