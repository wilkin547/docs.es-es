---
title: IMetaDataTables::GetString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f817fa3f24bebf3303c656bd02c4d93d1d1431b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781397"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="cf6ef-102">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="cf6ef-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="cf6ef-103">Obtiene la cadena en el índice especificado de la columna de tabla en el ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="cf6ef-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf6ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf6ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf6ef-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="cf6ef-106">[in] Índice en el que se va a empezar a buscar el valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="cf6ef-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="cf6ef-107">[out] Un puntero a un puntero al valor de cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="cf6ef-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf6ef-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf6ef-108">Requirements</span></span>  
 <span data-ttu-id="cf6ef-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf6ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf6ef-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf6ef-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf6ef-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf6ef-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf6ef-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf6ef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6ef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf6ef-113">See also</span></span>

- [<span data-ttu-id="cf6ef-114">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf6ef-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cf6ef-115">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf6ef-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
