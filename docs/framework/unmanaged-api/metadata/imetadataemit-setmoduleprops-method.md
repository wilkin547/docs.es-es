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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042983"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="939fd-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="939fd-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="939fd-103">Actualiza las referencias a un módulo definido por una llamada anterior a [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="939fd-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="939fd-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="939fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="939fd-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="939fd-106">[in] El nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="939fd-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="939fd-107">Esto es sólo el nombre de archivo y no el nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="939fd-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="939fd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="939fd-108">Requirements</span></span>  
 <span data-ttu-id="939fd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="939fd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="939fd-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="939fd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="939fd-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="939fd-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="939fd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="939fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="939fd-113">See also</span></span>

- [<span data-ttu-id="939fd-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="939fd-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="939fd-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="939fd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
