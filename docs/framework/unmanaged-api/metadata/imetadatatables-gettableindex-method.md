---
description: 'Más información acerca de: IMetaDataTables:: Gettableindex ((método)'
title: IMetaDataTables::GetTableIndex (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: d42a42a1a19a67fada17bbe1016f7e324cd1c287
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687732"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="4f75d-103">IMetaDataTables::GetTableIndex (Método)</span><span class="sxs-lookup"><span data-stu-id="4f75d-103">IMetaDataTables::GetTableIndex Method</span></span>

<span data-ttu-id="4f75d-104">Obtiene el índice de la tabla a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="4f75d-104">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f75d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f75d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f75d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f75d-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="4f75d-107">de El token que hace referencia a la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f75d-107">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="4f75d-108">enuncia Puntero al índice devuelto para la tabla a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4f75d-108">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f75d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f75d-109">Remarks</span></span>  

 <span data-ttu-id="4f75d-110">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="4f75d-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="4f75d-111">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="4f75d-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="4f75d-112">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="4f75d-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f75d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f75d-113">Requirements</span></span>  

 <span data-ttu-id="4f75d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f75d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f75d-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f75d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f75d-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f75d-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f75d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f75d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f75d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f75d-118">See also</span></span>

- [<span data-ttu-id="4f75d-119">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f75d-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="4f75d-120">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f75d-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
