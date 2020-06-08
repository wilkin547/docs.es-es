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
ms.openlocfilehash: 6f4764f016360a2ec0ab054b7a89ccb3f86aeb43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490229"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="7b69e-102">IMetaDataTables::GetNextString (Método)</span><span class="sxs-lookup"><span data-stu-id="7b69e-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="7b69e-103">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="7b69e-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b69e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b69e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b69e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b69e-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="7b69e-106">de Valor de índice de una columna de la tabla de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7b69e-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="7b69e-107">enuncia Puntero al índice de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="7b69e-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b69e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b69e-108">Requirements</span></span>  
 <span data-ttu-id="7b69e-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b69e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b69e-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b69e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b69e-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7b69e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b69e-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b69e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b69e-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7b69e-113">See also</span></span>

- [<span data-ttu-id="7b69e-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b69e-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7b69e-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b69e-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
