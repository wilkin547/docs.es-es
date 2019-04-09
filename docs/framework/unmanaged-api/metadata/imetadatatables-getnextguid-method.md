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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110474"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="9636c-102">IMetaDataTables::GetNextGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="9636c-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="9636c-103">Obtiene el índice del siguiente valor de GUID de la columna de tabla actual.</span><span class="sxs-lookup"><span data-stu-id="9636c-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9636c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9636c-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9636c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9636c-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="9636c-106">[in] El valor de índice de una columna de tabla GUID.</span><span class="sxs-lookup"><span data-stu-id="9636c-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9636c-107">[out] Un puntero al índice del siguiente valor de GUID.</span><span class="sxs-lookup"><span data-stu-id="9636c-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9636c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9636c-108">Remarks</span></span>  
 <span data-ttu-id="9636c-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="9636c-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="9636c-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "Partition II: Definición de metadatos y la semántica".</span><span class="sxs-lookup"><span data-stu-id="9636c-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="9636c-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="9636c-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9636c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9636c-112">Requirements</span></span>  
 <span data-ttu-id="9636c-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9636c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9636c-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="9636c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9636c-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9636c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9636c-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9636c-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9636c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9636c-117">See also</span></span>

- [<span data-ttu-id="9636c-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9636c-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="9636c-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9636c-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
