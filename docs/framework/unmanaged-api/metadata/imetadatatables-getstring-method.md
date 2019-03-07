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
ms.openlocfilehash: c71efb9156c503ac88ba558ad7a9f757b608bf40
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466159"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="a8bb8-102">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="a8bb8-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="a8bb8-103">Obtiene la cadena en el índice especificado de la columna de tabla en el ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8bb8-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8bb8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8bb8-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="a8bb8-106">[in] Índice en el que se va a empezar a buscar el valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="a8bb8-107">[out] Un puntero a un puntero al valor de cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bb8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8bb8-108">Requirements</span></span>  
 <span data-ttu-id="a8bb8-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bb8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bb8-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8bb8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8bb8-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8bb8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8bb8-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bb8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bb8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8bb8-113">See also</span></span>
- [<span data-ttu-id="a8bb8-114">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8bb8-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a8bb8-115">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8bb8-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
