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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb7e2ed7b076cfa20064902b3592c8f958efc0ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917052"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="49d0e-102">ICorDebugFunction2::EnumerateNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="49d0e-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="49d0e-103">Obtiene un puntero de interfaz a un objeto ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="49d0e-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49d0e-104">`EnumerateNativeCode`no se implementa en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49d0e-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d0e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49d0e-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="49d0e-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49d0e-106">Requirements</span></span>  
 <span data-ttu-id="49d0e-107">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="49d0e-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
