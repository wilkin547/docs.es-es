---
title: IMetaDataTables::GetNextUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b9e729732175b7249e4d3be91996bc5e4050855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450211"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="40eb1-102">IMetaDataTables::GetNextUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="40eb1-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="40eb1-103">Obtiene el índice de la fila que contiene la siguiente cadena codificados de forma rígida en la columna de tabla actual.</span><span class="sxs-lookup"><span data-stu-id="40eb1-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40eb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40eb1-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40eb1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40eb1-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="40eb1-106">[in] Un valor de índice de la columna de cadena actual.</span><span class="sxs-lookup"><span data-stu-id="40eb1-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="40eb1-107">[out] Puntero al índice de fila de la cadena siguiente en la columna.</span><span class="sxs-lookup"><span data-stu-id="40eb1-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40eb1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40eb1-108">Remarks</span></span>  
 <span data-ttu-id="40eb1-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="40eb1-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="40eb1-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="40eb1-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="40eb1-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="40eb1-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40eb1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40eb1-112">Requirements</span></span>  
 <span data-ttu-id="40eb1-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40eb1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40eb1-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40eb1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40eb1-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40eb1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40eb1-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40eb1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eb1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40eb1-117">See Also</span></span>  
 [<span data-ttu-id="40eb1-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40eb1-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="40eb1-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40eb1-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
