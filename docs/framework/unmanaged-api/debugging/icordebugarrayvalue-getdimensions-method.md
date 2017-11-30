---
title: "ICorDebugArrayValue::GetDimensions (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetDimensions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364035a0b6e26f5649ef9be5839d096be2fb02dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="4a774-102">ICorDebugArrayValue::GetDimensions (Método)</span><span class="sxs-lookup"><span data-stu-id="4a774-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="4a774-103">Obtiene el número de elementos de cada dimensión de esta matriz.</span><span class="sxs-lookup"><span data-stu-id="4a774-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a774-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a774-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a774-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a774-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="4a774-106">[in] El número de dimensiones de este objeto ICorDebugArrayValue.</span><span class="sxs-lookup"><span data-stu-id="4a774-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="4a774-107">Este valor también es el tamaño de la `dims` matriz porque su tamaño es igual al número de dimensiones de la `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="4a774-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="4a774-108">[out] Una matriz de enteros, cada uno de los cuales especifica el número de elementos de una dimensión en este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="4a774-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a774-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a774-109">Requirements</span></span>  
 <span data-ttu-id="4a774-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a774-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a774-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a774-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a774-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a774-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a774-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a774-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
