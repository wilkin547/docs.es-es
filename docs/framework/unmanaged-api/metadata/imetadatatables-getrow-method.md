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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870892"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="30bf8-102">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="30bf8-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="30bf8-103">Obtiene la fila en el índice de fila especificado, en la tabla en el índice de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="30bf8-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30bf8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30bf8-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30bf8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30bf8-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="30bf8-106">[in] El índice de la tabla desde el que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="30bf8-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="30bf8-107">[in] El índice de la fila que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="30bf8-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="30bf8-108">[out] Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="30bf8-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30bf8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30bf8-109">Remarks</span></span>  
 <span data-ttu-id="30bf8-110">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="30bf8-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="30bf8-111">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente en "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="30bf8-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="30bf8-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="30bf8-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30bf8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30bf8-113">Requirements</span></span>  
 <span data-ttu-id="30bf8-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30bf8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30bf8-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="30bf8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30bf8-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30bf8-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30bf8-117">**Versiones de .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30bf8-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30bf8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="30bf8-118">See Also</span></span>  
 [<span data-ttu-id="30bf8-119">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30bf8-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="30bf8-120">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30bf8-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
