---
title: IMetaDataTables::GetNextString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175257"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="c13de-102">IMetaDataTables::GetNextString (Método)</span><span class="sxs-lookup"><span data-stu-id="c13de-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="c13de-103">Obtiene el índice de la siguiente cadena de la columna de tabla actual.</span><span class="sxs-lookup"><span data-stu-id="c13de-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c13de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c13de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c13de-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="c13de-106">[en] El valor de índice de una columna de tabla de cadenas.</span><span class="sxs-lookup"><span data-stu-id="c13de-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="c13de-107">[fuera] Un puntero al índice de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="c13de-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13de-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c13de-108">Requirements</span></span>  
 <span data-ttu-id="c13de-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c13de-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13de-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c13de-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c13de-111">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c13de-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c13de-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13de-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c13de-113">See also</span></span>

- [<span data-ttu-id="c13de-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c13de-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c13de-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c13de-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
