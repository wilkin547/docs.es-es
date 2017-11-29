---
title: "ICorDebugReferenceValue::Dereference (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.Dereference
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4eb3287612a8301d551a1443d803e60e4d03f7db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="ef448-102">ICorDebugReferenceValue::Dereference (Método)</span><span class="sxs-lookup"><span data-stu-id="ef448-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="ef448-103">Obtiene el objeto al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ef448-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef448-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef448-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef448-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef448-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="ef448-106">[out] Un puntero a la dirección de ICorDebugValue que representa el objeto al que apunta este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="ef448-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef448-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef448-107">Remarks</span></span>  
 <span data-ttu-id="ef448-108">La `ICorDebugValue` objeto es válido solo mientras aún no se ha deshabilitado su referencia.</span><span class="sxs-lookup"><span data-stu-id="ef448-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef448-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef448-109">Requirements</span></span>  
 <span data-ttu-id="ef448-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef448-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef448-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef448-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef448-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef448-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef448-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef448-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
