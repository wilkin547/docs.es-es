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
ms.openlocfilehash: 9973ef77a064dfe144d742d8cf12d8ae8dd2565f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447412"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="f099e-102">IMetaDataTables::GetRow (Método)</span><span class="sxs-lookup"><span data-stu-id="f099e-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="f099e-103">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="f099e-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f099e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f099e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f099e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f099e-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="f099e-106">de Índice de la tabla de la que se recuperará la fila.</span><span class="sxs-lookup"><span data-stu-id="f099e-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="f099e-107">de Índice de la fila que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="f099e-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="f099e-108">enuncia Un puntero a un puntero a la fila.</span><span class="sxs-lookup"><span data-stu-id="f099e-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f099e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f099e-109">Remarks</span></span>  
 <span data-ttu-id="f099e-110">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="f099e-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f099e-111">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="f099e-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f099e-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="f099e-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f099e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f099e-113">Requirements</span></span>  
 <span data-ttu-id="f099e-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f099e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f099e-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f099e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f099e-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f099e-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f099e-117">**.NET Framework versiones**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f099e-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f099e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f099e-118">See also</span></span>

- [<span data-ttu-id="f099e-119">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f099e-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f099e-120">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f099e-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
