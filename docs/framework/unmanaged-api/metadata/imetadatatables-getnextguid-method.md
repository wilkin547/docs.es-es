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
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937795"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="45c7d-102">IMetaDataTables::GetNextGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="45c7d-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="45c7d-103">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="45c7d-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45c7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45c7d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="45c7d-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="45c7d-106">de Valor de índice de una columna de la tabla GUID.</span><span class="sxs-lookup"><span data-stu-id="45c7d-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="45c7d-107">enuncia Puntero al índice del siguiente valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="45c7d-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45c7d-108">Notas</span><span class="sxs-lookup"><span data-stu-id="45c7d-108">Remarks</span></span>  

  <span data-ttu-id="45c7d-109">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="45c7d-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="45c7d-110">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="45c7d-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="45c7d-111">La documentación está disponible en línea; consulte [los C# estándares de ECMA y Common Language Infrastructure](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="45c7d-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45c7d-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="45c7d-112">Requirements</span></span>  
 <span data-ttu-id="45c7d-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c7d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c7d-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45c7d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45c7d-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45c7d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45c7d-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c7d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c7d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="45c7d-117">See also</span></span>

- [<span data-ttu-id="45c7d-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45c7d-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="45c7d-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45c7d-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
