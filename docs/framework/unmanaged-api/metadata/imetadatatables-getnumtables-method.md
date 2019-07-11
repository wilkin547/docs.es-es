---
title: IMetaDataTables::GetNumTables (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb26a96c46b01a2981afba0ac6b405c0b50f6d9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781421"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="48d0f-102">IMetaDataTables::GetNumTables (Método)</span><span class="sxs-lookup"><span data-stu-id="48d0f-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="48d0f-103">Obtiene el número de tablas en el ámbito del elemento actual `IMetaDataTables` instancia.</span><span class="sxs-lookup"><span data-stu-id="48d0f-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d0f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48d0f-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="48d0f-106">[out] Un puntero al número de tablas en el ámbito de la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="48d0f-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d0f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d0f-107">Requirements</span></span>  
 <span data-ttu-id="48d0f-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d0f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d0f-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="48d0f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48d0f-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48d0f-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48d0f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d0f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d0f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="48d0f-112">See also</span></span>

- [<span data-ttu-id="48d0f-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48d0f-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="48d0f-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48d0f-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
