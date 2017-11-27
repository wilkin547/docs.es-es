---
title: "IMetaDataTables::GetTableIndex (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d49e1258011d68a6278d1c40500386024a2cb0d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="d06e3-102">IMetaDataTables::GetTableIndex (Método)</span><span class="sxs-lookup"><span data-stu-id="d06e3-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="d06e3-103">Obtiene el índice de la tabla al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d06e3-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d06e3-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d06e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d06e3-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="d06e3-106">[in] El token que hace referencia a la tabla.</span><span class="sxs-lookup"><span data-stu-id="d06e3-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="d06e3-107">[out] Un puntero al índice devuelto para la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="d06e3-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d06e3-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d06e3-108">Remarks</span></span>  
 <span data-ttu-id="d06e3-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="d06e3-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d06e3-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="d06e3-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d06e3-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="d06e3-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d06e3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d06e3-112">Requirements</span></span>  
 <span data-ttu-id="d06e3-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d06e3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06e3-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d06e3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d06e3-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d06e3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d06e3-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d06e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06e3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d06e3-117">See Also</span></span>  
 [<span data-ttu-id="d06e3-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d06e3-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="d06e3-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d06e3-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
