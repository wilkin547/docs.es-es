---
title: "IMetaDataEmit::SetModuleProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e67acee8092fa20500038bb25e542c3dddb3233e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="47696-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="47696-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="47696-103">Actualiza las referencias a un módulo definido por una llamada anterior a [IMetaDataEmit:: DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="47696-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47696-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47696-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47696-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47696-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="47696-106">[in] El nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="47696-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="47696-107">Esto es solo el nombre de archivo y no el nombre de ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="47696-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47696-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47696-108">Requirements</span></span>  
 <span data-ttu-id="47696-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47696-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47696-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47696-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47696-111">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47696-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47696-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47696-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47696-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="47696-113">See Also</span></span>  
 [<span data-ttu-id="47696-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47696-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="47696-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47696-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
