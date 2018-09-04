---
title: IMetaDataTables::GetNextGuid (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3273f89d61314db2ae36c572f2ca520f28e63e3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552879"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="99d8b-102">IMetaDataTables::GetNextGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="99d8b-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="99d8b-103">Obtiene el índice del siguiente valor de GUID de la columna de tabla actual.</span><span class="sxs-lookup"><span data-stu-id="99d8b-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99d8b-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99d8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99d8b-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="99d8b-106">[in] El valor de índice de una columna de tabla GUID.</span><span class="sxs-lookup"><span data-stu-id="99d8b-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="99d8b-107">[out] Un puntero al índice del siguiente valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="99d8b-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99d8b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99d8b-108">Remarks</span></span>  
 <span data-ttu-id="99d8b-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="99d8b-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="99d8b-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente en "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="99d8b-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="99d8b-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="99d8b-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d8b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99d8b-112">Requirements</span></span>  
 <span data-ttu-id="99d8b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d8b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d8b-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99d8b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99d8b-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99d8b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99d8b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d8b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d8b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="99d8b-117">See Also</span></span>  
 [<span data-ttu-id="99d8b-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d8b-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="99d8b-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d8b-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
