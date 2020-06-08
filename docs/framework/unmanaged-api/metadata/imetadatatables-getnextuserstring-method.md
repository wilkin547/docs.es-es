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
ms.openlocfilehash: 3490eec7c3b59ab8f4158498e2731773b6491b42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490190"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="c2dd1-102">IMetaDataTables::GetNextUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="c2dd1-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="c2dd1-103">Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="c2dd1-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2dd1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2dd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2dd1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2dd1-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="c2dd1-106">de Un valor de índice de la columna de cadena actual.</span><span class="sxs-lookup"><span data-stu-id="c2dd1-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="c2dd1-107">enuncia Puntero al índice de fila de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="c2dd1-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2dd1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2dd1-108">Remarks</span></span>  
 <span data-ttu-id="c2dd1-109">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="c2dd1-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="c2dd1-110">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="c2dd1-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="c2dd1-111">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="c2dd1-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2dd1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2dd1-112">Requirements</span></span>  
 <span data-ttu-id="c2dd1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2dd1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2dd1-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c2dd1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2dd1-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c2dd1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2dd1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2dd1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dd1-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c2dd1-117">See also</span></span>

- [<span data-ttu-id="c2dd1-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2dd1-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c2dd1-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2dd1-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
