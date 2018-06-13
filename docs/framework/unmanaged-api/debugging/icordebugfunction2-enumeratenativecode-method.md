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
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411793"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>ICorDebugFunction2::EnumerateNativeCode (Método)
Obtiene un puntero de interfaz a un objeto ICorDebugCodeEnum que contiene las instrucciones de código nativo en la función que hace referencia este objeto ICorDebugFunction2.  
  
> [!NOTE]
>  `EnumerateNativeCode` no se implementa en la versión actual de .NET Framework.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorDebug.idl, CorDebug.h
