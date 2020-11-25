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
ms.openlocfilehash: b79dbdd64ac171d1bc4cd30b96ee76b4a853afb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727255"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="b6e80-102">IMetaDataTables::GetNextString (Método)</span><span class="sxs-lookup"><span data-stu-id="b6e80-102">IMetaDataTables::GetNextString Method</span></span>

<span data-ttu-id="b6e80-103">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="b6e80-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6e80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6e80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6e80-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="b6e80-106">de Valor de índice de una columna de la tabla de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b6e80-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="b6e80-107">enuncia Puntero al índice de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="b6e80-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e80-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6e80-108">Requirements</span></span>  

 <span data-ttu-id="b6e80-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6e80-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e80-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6e80-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6e80-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6e80-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6e80-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e80-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e80-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6e80-113">See also</span></span>

- [<span data-ttu-id="b6e80-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6e80-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b6e80-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6e80-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
