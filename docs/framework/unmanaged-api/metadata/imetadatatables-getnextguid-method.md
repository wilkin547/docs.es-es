---
description: 'Más información acerca de: IMetaDataTables:: Getnextguid ((método)'
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
ms.openlocfilehash: 86c248bf503410a07fc0b4cf622694c4da213c34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688109"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="b066a-103">IMetaDataTables::GetNextGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="b066a-103">IMetaDataTables::GetNextGuid Method</span></span>

<span data-ttu-id="b066a-104">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="b066a-104">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b066a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b066a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b066a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b066a-106">Parameters</span></span>  

 `ixGuid`  
 <span data-ttu-id="b066a-107">de Valor de índice de una columna de la tabla GUID.</span><span class="sxs-lookup"><span data-stu-id="b066a-107">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="b066a-108">enuncia Puntero al índice del siguiente valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="b066a-108">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b066a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b066a-109">Remarks</span></span>  

  <span data-ttu-id="b066a-110">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="b066a-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="b066a-111">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="b066a-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="b066a-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="b066a-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b066a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b066a-113">Requirements</span></span>  

 <span data-ttu-id="b066a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b066a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b066a-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b066a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b066a-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b066a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b066a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b066a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b066a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b066a-118">See also</span></span>

- [<span data-ttu-id="b066a-119">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b066a-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b066a-120">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b066a-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
