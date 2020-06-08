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
ms.openlocfilehash: 645a9913d0de6f93e59df3dd8ba7267ddb13b41b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490268"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="a05ae-102">IMetaDataTables::GetNextGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="a05ae-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="a05ae-103">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="a05ae-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a05ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a05ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a05ae-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="a05ae-106">de Valor de índice de una columna de la tabla GUID.</span><span class="sxs-lookup"><span data-stu-id="a05ae-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a05ae-107">enuncia Puntero al índice del siguiente valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="a05ae-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a05ae-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a05ae-108">Remarks</span></span>  

  <span data-ttu-id="a05ae-109">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="a05ae-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="a05ae-110">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="a05ae-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="a05ae-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="a05ae-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a05ae-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a05ae-112">Requirements</span></span>  
 <span data-ttu-id="a05ae-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a05ae-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a05ae-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a05ae-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a05ae-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a05ae-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a05ae-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a05ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05ae-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a05ae-117">See also</span></span>

- [<span data-ttu-id="a05ae-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a05ae-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a05ae-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a05ae-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
