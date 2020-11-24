---
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
ms.openlocfilehash: 52d70a76bdf8380d320edb6e8188443070a36b1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672566"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="d6d13-102">IMetaDataTables::GetTableIndex (Método)</span><span class="sxs-lookup"><span data-stu-id="d6d13-102">IMetaDataTables::GetTableIndex Method</span></span>

<span data-ttu-id="d6d13-103">Obtiene el índice de la tabla a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d6d13-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6d13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6d13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6d13-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="d6d13-106">de El token que hace referencia a la tabla.</span><span class="sxs-lookup"><span data-stu-id="d6d13-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="d6d13-107">enuncia Puntero al índice devuelto para la tabla a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d6d13-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6d13-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6d13-108">Remarks</span></span>  

 <span data-ttu-id="d6d13-109">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="d6d13-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d6d13-110">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="d6d13-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d6d13-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="d6d13-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6d13-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6d13-112">Requirements</span></span>  

 <span data-ttu-id="d6d13-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6d13-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6d13-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d6d13-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6d13-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6d13-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6d13-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6d13-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d13-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6d13-117">See also</span></span>

- [<span data-ttu-id="d6d13-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6d13-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d6d13-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6d13-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
