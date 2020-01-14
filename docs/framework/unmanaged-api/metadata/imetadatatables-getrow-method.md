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
ms.openlocfilehash: 9ac6eba18ae23dc80a8dc90383aa67cfe41b39ff
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937407"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="e5fc8-102">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="e5fc8-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="e5fc8-103">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="e5fc8-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5fc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5fc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5fc8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e5fc8-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="e5fc8-106">de Índice de la tabla de la que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="e5fc8-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="e5fc8-107">de Índice de la fila que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="e5fc8-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="e5fc8-108">enuncia Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="e5fc8-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5fc8-109">Notas</span><span class="sxs-lookup"><span data-stu-id="e5fc8-109">Remarks</span></span>  

  <span data-ttu-id="e5fc8-110">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="e5fc8-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="e5fc8-111">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="e5fc8-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="e5fc8-112">La documentación está disponible en línea; consulte [los C# estándares de ECMA y Common Language Infrastructure](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="e5fc8-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5fc8-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e5fc8-113">Requirements</span></span>  
 <span data-ttu-id="e5fc8-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5fc8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5fc8-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e5fc8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5fc8-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e5fc8-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5fc8-117">**.NET Framework versiones**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5fc8-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fc8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5fc8-118">See also</span></span>

- [<span data-ttu-id="e5fc8-119">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5fc8-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="e5fc8-120">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5fc8-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
