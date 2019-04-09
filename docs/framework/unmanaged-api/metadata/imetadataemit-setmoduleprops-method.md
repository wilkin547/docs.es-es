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
ms.openlocfilehash: 651659a48ba9950cdd837889c4491c66fe40b507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202968"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="5a756-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5a756-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="5a756-103">Actualiza las referencias a un módulo definido por una llamada anterior a [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a756-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a756-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a756-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a756-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a756-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5a756-106">[in] El nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="5a756-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="5a756-107">Esto es sólo el nombre de archivo y no el nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="5a756-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a756-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a756-108">Requirements</span></span>  
 <span data-ttu-id="5a756-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a756-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a756-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a756-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a756-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a756-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5a756-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5a756-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a756-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a756-113">See also</span></span>

- [<span data-ttu-id="5a756-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a756-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5a756-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a756-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
