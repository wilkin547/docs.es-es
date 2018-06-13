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
ms.openlocfilehash: 954b4df6b341e18c5a995b57541a72e236278c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449600"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="89b21-102">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="89b21-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="89b21-103">Obtiene la fila en el índice de fila especificado, en la tabla en el índice de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="89b21-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89b21-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89b21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89b21-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="89b21-106">[in] El índice de la tabla desde el que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="89b21-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="89b21-107">[in] El índice de la fila que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="89b21-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="89b21-108">[out] Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="89b21-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89b21-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89b21-109">Remarks</span></span>  
 <span data-ttu-id="89b21-110">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="89b21-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="89b21-111">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="89b21-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="89b21-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="89b21-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89b21-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89b21-113">Requirements</span></span>  
 <span data-ttu-id="89b21-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89b21-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89b21-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89b21-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89b21-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89b21-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89b21-117">**Versiones de .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89b21-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b21-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="89b21-118">See Also</span></span>  
 [<span data-ttu-id="89b21-119">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89b21-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="89b21-120">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89b21-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
