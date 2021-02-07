---
description: 'Más información acerca de: IMetaDataTables:: GetRow (método)'
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
ms.openlocfilehash: f3888bbb53339dc60eb0c2d36f2d7383e5f8c228
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687823"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="3ce6c-103">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="3ce6c-103">IMetaDataTables::GetRow Method</span></span>

<span data-ttu-id="3ce6c-104">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="3ce6c-104">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ce6c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ce6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ce6c-106">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="3ce6c-107">de Índice de la tabla de la que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="3ce6c-107">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="3ce6c-108">de Índice de la fila que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="3ce6c-108">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="3ce6c-109">enuncia Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="3ce6c-109">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce6c-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ce6c-110">Remarks</span></span>  

  <span data-ttu-id="3ce6c-111">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="3ce6c-111">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="3ce6c-112">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="3ce6c-112">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="3ce6c-113">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="3ce6c-113">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ce6c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ce6c-114">Requirements</span></span>  

 <span data-ttu-id="3ce6c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ce6c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce6c-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3ce6c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ce6c-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ce6c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ce6c-118">**.NET Framework versiones**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce6c-118">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce6c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ce6c-119">See also</span></span>

- [<span data-ttu-id="3ce6c-120">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ce6c-120">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="3ce6c-121">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ce6c-121">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
