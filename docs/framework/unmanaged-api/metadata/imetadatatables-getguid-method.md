---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70a22e7e37a0fd88bcb8673846f5313d35971a15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992256"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="accd6-102">IMetaDataTables::GetGuid (Método)</span><span class="sxs-lookup"><span data-stu-id="accd6-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="accd6-103">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="accd6-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accd6-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accd6-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="accd6-106">[in] El índice de la fila de la que se va a obtener el GUID.</span><span class="sxs-lookup"><span data-stu-id="accd6-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="accd6-107">[out] Un puntero a un puntero al GUID.</span><span class="sxs-lookup"><span data-stu-id="accd6-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="accd6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="accd6-108">Remarks</span></span>  
 <span data-ttu-id="accd6-109">No se recomienda el uso de este método, porque no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="accd6-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="accd6-110">Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "Partition II: Definición de metadatos y la semántica".</span><span class="sxs-lookup"><span data-stu-id="accd6-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="accd6-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="accd6-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accd6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accd6-112">Requirements</span></span>  
 <span data-ttu-id="accd6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accd6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accd6-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="accd6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="accd6-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="accd6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="accd6-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accd6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accd6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="accd6-117">See also</span></span>

- [<span data-ttu-id="accd6-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="accd6-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="accd6-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="accd6-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
