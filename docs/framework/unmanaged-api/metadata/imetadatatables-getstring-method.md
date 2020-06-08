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
ms.openlocfilehash: 41e7b8193ce3288d526db8d7d8c289b0a053ee4e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489761"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="3952b-102">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="3952b-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="3952b-103">Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="3952b-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3952b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3952b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3952b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3952b-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="3952b-106">de Índice en el que se va a empezar a buscar el valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="3952b-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="3952b-107">enuncia Un puntero a un puntero al valor de cadena devuelto.</span><span class="sxs-lookup"><span data-stu-id="3952b-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3952b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3952b-108">Requirements</span></span>  
 <span data-ttu-id="3952b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3952b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3952b-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3952b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3952b-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3952b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3952b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3952b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3952b-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="3952b-113">See also</span></span>

- [<span data-ttu-id="3952b-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3952b-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="3952b-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3952b-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
