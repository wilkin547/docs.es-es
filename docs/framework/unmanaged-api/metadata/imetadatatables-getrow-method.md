---
title: IMetaDataTables::GetRow (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177117"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="b6887-102">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="b6887-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="b6887-103">Obtiene la fila en el índice de fila especificado, en la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="b6887-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6887-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6887-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6887-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6887-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="b6887-106">[en] El índice de la tabla desde la que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="b6887-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="b6887-107">[en] El índice de la fila que se ha de obtener.</span><span class="sxs-lookup"><span data-stu-id="b6887-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="b6887-108">[fuera] Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="b6887-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6887-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b6887-109">Remarks</span></span>  

  <span data-ttu-id="b6887-110">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="b6887-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="b6887-111">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="b6887-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="b6887-112">La documentación está disponible en línea; Véanse los estándares de infraestructura de [ECMA C y Lenguaje Común](../../../standard/components.md#applicable-standards) y la norma [ECMA-335 - Common Language Infrastructure (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)</span><span class="sxs-lookup"><span data-stu-id="b6887-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6887-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6887-113">Requirements</span></span>  
 <span data-ttu-id="b6887-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6887-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6887-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b6887-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6887-116">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6887-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6887-117">**Versiones de .NET Framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6887-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6887-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6887-118">See also</span></span>

- [<span data-ttu-id="b6887-119">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6887-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b6887-120">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6887-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
