---
title: IMetaDataTables::GetGuid (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175283"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="5baf7-102">IMetaDataTables::GetGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="5baf7-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="5baf7-103">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="5baf7-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5baf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5baf7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5baf7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5baf7-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="5baf7-106">[en] El índice de la fila desde la que se obtiene el GUID.</span><span class="sxs-lookup"><span data-stu-id="5baf7-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="5baf7-107">[fuera] Un puntero a un puntero al GUID.</span><span class="sxs-lookup"><span data-stu-id="5baf7-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5baf7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5baf7-108">Remarks</span></span>  

  <span data-ttu-id="5baf7-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="5baf7-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="5baf7-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="5baf7-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="5baf7-111">La documentación está disponible en línea; Véanse los estándares de infraestructura de [ECMA C y Lenguaje Común](../../../standard/components.md#applicable-standards) y la norma [ECMA-335 - Common Language Infrastructure (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="5baf7-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5baf7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5baf7-112">Requirements</span></span>  
 <span data-ttu-id="5baf7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5baf7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5baf7-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5baf7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5baf7-115">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5baf7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5baf7-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5baf7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5baf7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5baf7-117">See also</span></span>

- [<span data-ttu-id="5baf7-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5baf7-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5baf7-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5baf7-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
