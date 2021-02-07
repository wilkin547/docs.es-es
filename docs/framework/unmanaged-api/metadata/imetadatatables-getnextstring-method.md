---
description: 'Más información acerca de: IMetaDataTables:: Getnextstring ((método)'
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
ms.openlocfilehash: b3c4f94a2659b83c89bef322517465a585b63ddc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688018"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="7b7aa-103">IMetaDataTables::GetNextString (Método)</span><span class="sxs-lookup"><span data-stu-id="7b7aa-103">IMetaDataTables::GetNextString Method</span></span>

<span data-ttu-id="7b7aa-104">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-104">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b7aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b7aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b7aa-106">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="7b7aa-107">de Valor de índice de una columna de la tabla de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-107">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="7b7aa-108">enuncia Puntero al índice de la siguiente cadena de la columna.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-108">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b7aa-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b7aa-109">Requirements</span></span>  

 <span data-ttu-id="7b7aa-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b7aa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b7aa-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b7aa-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b7aa-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b7aa-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b7aa-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b7aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7aa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b7aa-114">See also</span></span>

- [<span data-ttu-id="7b7aa-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b7aa-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7b7aa-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b7aa-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
