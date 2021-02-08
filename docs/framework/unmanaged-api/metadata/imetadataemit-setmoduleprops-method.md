---
description: 'Más información sobre: IMetaDataEmit:: SetModuleProps ((método)'
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
ms.openlocfilehash: 0fc68a3f40871ddbb70cef885789ae7fe8ae0cba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772034"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="faa80-103">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="faa80-103">IMetaDataEmit::SetModuleProps Method</span></span>

<span data-ttu-id="faa80-104">Actualiza las referencias a un módulo definido por una llamada anterior a [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="faa80-104">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa80-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="faa80-105">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faa80-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="faa80-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="faa80-107">de Nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="faa80-107">[in] The module name in Unicode.</span></span> <span data-ttu-id="faa80-108">Este es el nombre de archivo únicamente y no el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="faa80-108">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa80-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faa80-109">Requirements</span></span>  

 <span data-ttu-id="faa80-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faa80-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa80-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="faa80-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="faa80-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="faa80-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faa80-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa80-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa80-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="faa80-114">See also</span></span>

- [<span data-ttu-id="faa80-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="faa80-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="faa80-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="faa80-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
