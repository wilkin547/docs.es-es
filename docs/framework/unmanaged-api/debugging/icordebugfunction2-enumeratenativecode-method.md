---
title: ICorDebugFunction2::EnumerateNativeCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
ms.openlocfilehash: d5b24ee02a682b38dcf0cb3449f0dff197e91bf9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137830"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="4260d-102">ICorDebugFunction2::EnumerateNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="4260d-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="4260d-103">Obtiene un puntero de interfaz a un objeto ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="4260d-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4260d-104">`EnumerateNativeCode` no se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4260d-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4260d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4260d-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4260d-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4260d-106">Requirements</span></span>  
 <span data-ttu-id="4260d-107">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4260d-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
