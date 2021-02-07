---
description: 'Más información acerca de: IMetaDataTables:: GetGuid (método)'
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
ms.openlocfilehash: 9c3b8b11bb2f6a1abc3c55d953e1cbfbd7ee8622
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688174"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="23edb-103">IMetaDataTables::GetGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="23edb-103">IMetaDataTables::GetGuid Method</span></span>

<span data-ttu-id="23edb-104">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="23edb-104">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23edb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23edb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23edb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23edb-106">Parameters</span></span>  

 `ixGuid`  
 <span data-ttu-id="23edb-107">de Índice de la fila de la que se va a obtener el GUID.</span><span class="sxs-lookup"><span data-stu-id="23edb-107">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="23edb-108">enuncia Un puntero a un puntero al GUID.</span><span class="sxs-lookup"><span data-stu-id="23edb-108">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23edb-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23edb-109">Remarks</span></span>  

  <span data-ttu-id="23edb-110">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="23edb-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="23edb-111">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="23edb-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="23edb-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="23edb-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23edb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23edb-113">Requirements</span></span>  

 <span data-ttu-id="23edb-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23edb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23edb-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="23edb-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23edb-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23edb-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23edb-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23edb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23edb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="23edb-118">See also</span></span>

- [<span data-ttu-id="23edb-119">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23edb-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="23edb-120">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23edb-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
