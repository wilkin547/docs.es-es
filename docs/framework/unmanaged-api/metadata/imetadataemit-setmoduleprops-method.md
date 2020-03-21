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
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175621"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="ed863-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ed863-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="ed863-103">Actualiza las referencias a un módulo definido por una llamada anterior a [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="ed863-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed863-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed863-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed863-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed863-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ed863-106">[en] El nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="ed863-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="ed863-107">Este es el nombre de archivo solamente y no el nombre de ruta de acceso completo.</span><span class="sxs-lookup"><span data-stu-id="ed863-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed863-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed863-108">Requirements</span></span>  
 <span data-ttu-id="ed863-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed863-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed863-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed863-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed863-111">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed863-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed863-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed863-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed863-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed863-113">See also</span></span>

- [<span data-ttu-id="ed863-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed863-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ed863-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed863-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
