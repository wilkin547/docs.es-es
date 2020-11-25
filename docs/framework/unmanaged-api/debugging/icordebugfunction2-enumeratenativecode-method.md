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
ms.openlocfilehash: 2cac4a3120e842bde9ad708a251682421fd4ca93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696081"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>ICorDebugFunction2::EnumerateNativeCode (Método)

Obtiene un puntero de interfaz a un objeto ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.  
  
> [!NOTE]
> `EnumerateNativeCode` no se implementa en la versión actual del .NET Framework.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorDebug.idl, CorDebug.h
