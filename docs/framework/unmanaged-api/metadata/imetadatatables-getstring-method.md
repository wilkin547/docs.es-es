---
description: 'Más información acerca de: IMetaDataTables:: GetString (método)'
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
ms.openlocfilehash: 2104e30657a152d1b9a2ace743da9b126fb15d60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687797"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="b7a1d-103">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="b7a1d-103">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="b7a1d-104">Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="b7a1d-104">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7a1d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7a1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7a1d-106">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="b7a1d-107">de Índice en el que se va a empezar a buscar el valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="b7a1d-107">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="b7a1d-108">enuncia Un puntero a un puntero al valor de cadena devuelto.</span><span class="sxs-lookup"><span data-stu-id="b7a1d-108">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a1d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7a1d-109">Requirements</span></span>  

 <span data-ttu-id="b7a1d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a1d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a1d-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b7a1d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7a1d-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7a1d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7a1d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a1d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a1d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a1d-114">See also</span></span>

- [<span data-ttu-id="b7a1d-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7a1d-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b7a1d-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7a1d-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
