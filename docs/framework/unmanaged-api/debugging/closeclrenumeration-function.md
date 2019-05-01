---
title: CloseCLREnumeration (Función)
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60b6d9c302cd3af9f41e5a8dce62d7eb268c4198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961179"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration (Función)
Cierra los eventos de inicio continuo de common language runtime (CLR) válidos ubicados en una matriz de identificadores devueltos por la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)y libera la memoria para las matrices de ruta de acceso de identificadores y cadenas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pHandleArray`  
 [in] Puntero a la matriz de identificadores de eventos devueltos desde la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `pStringArray`  
 [in] Puntero a la matriz de rutas de acceso de cadena CLR devueltas desde el [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD que contiene el tamaño (longitud) de `pHandleArray` o `pStringArray` (son iguales).  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Identificadores abiertos por el [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) están cerrados, y se libera la memoria asignada para las matrices de identificadores y cadenas.  
  
 E_INVALIDARG  
 La longitud de `pHandleArray` no coincide con la longitud que se pasa en `dwArrayLength`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 La función no puede liberar la memoria para `pHandleArray` y `pStringArray`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim.h  
  
 **Biblioteca:** dbgshim.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
