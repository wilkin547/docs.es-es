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
ms.openlocfilehash: 6522dbc8e49d612fc4c0d9597a9b5f12edb2cfe1
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937787"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="7cff0-102">IMetaDataTables::GetNextUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="7cff0-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="7cff0-103">Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="7cff0-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cff0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cff0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cff0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7cff0-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="7cff0-106">de Un valor de índice de la columna de cadena actual.</span><span class="sxs-lookup"><span data-stu-id="7cff0-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="7cff0-107">enuncia Puntero al índice de fila de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="7cff0-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cff0-108">Notas</span><span class="sxs-lookup"><span data-stu-id="7cff0-108">Remarks</span></span>  
 <span data-ttu-id="7cff0-109">No se recomienda el uso de este método, ya que no devuelve resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="7cff0-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="7cff0-110">Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos".</span><span class="sxs-lookup"><span data-stu-id="7cff0-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="7cff0-111">La documentación está disponible en línea; consulte [los C# estándares de ECMA y Common Language Infrastructure](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="7cff0-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cff0-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7cff0-112">Requirements</span></span>  
 <span data-ttu-id="7cff0-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cff0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cff0-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7cff0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cff0-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7cff0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cff0-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cff0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cff0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cff0-117">See also</span></span>

- [<span data-ttu-id="7cff0-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cff0-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="7cff0-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cff0-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
