---
title: ICorDebugArrayValue::GetElement (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 500e01955666c7a8e2bd1dcf9d34afe3aeb6b421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403349"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="3a18f-102">ICorDebugArrayValue::GetElement (Método)</span><span class="sxs-lookup"><span data-stu-id="3a18f-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="3a18f-103">Obtiene el valor del elemento de matriz determinado.</span><span class="sxs-lookup"><span data-stu-id="3a18f-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a18f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a18f-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a18f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a18f-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="3a18f-106">[in] El número de dimensiones de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="3a18f-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="3a18f-107">Este valor también es el tamaño de la `indices` matriz porque su tamaño es igual al número de dimensiones de la `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="3a18f-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="3a18f-108">[in] Una matriz de valores de índice, cada uno de los cuales especifica una posición dentro de una dimensión de la `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="3a18f-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="3a18f-109">Este valor no debe ser null.</span><span class="sxs-lookup"><span data-stu-id="3a18f-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3a18f-110">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="3a18f-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a18f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a18f-111">Requirements</span></span>  
 <span data-ttu-id="3a18f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a18f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a18f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a18f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a18f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a18f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a18f-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a18f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
