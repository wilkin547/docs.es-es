---
title: "_EFN_StackTrace (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_StackTrace
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_StackTrace
helpviewer_keywords: _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905a44ee3187bc920d9342b043383a1500c28985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="efnstacktrace-function"></a>_EFN_StackTrace (Función)
Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Client`  
 [in] El cliente que se está depurando.  
  
 `wszTextOut`  
 [out] La representación de texto del seguimiento de pila.  
  
 `puiTextLength`  
 [out] Un puntero al número de caracteres en `wszTextOut`.  
  
 `pTransitionContexts`  
 [out] La matriz de contextos de transición.  
  
 `puiTransitionContextCount`  
 [out] Un puntero al número de contextos de transición en la matriz.  
  
 `uiSizeOfContext`  
 [in] El tamaño de la estructura de contexto.  
  
 `Flags`  
 [in] Establézcala en 0 o SOS_STACKTRACE_SHOWADDRESSES (0 x 01) para mostrar el registro EBP y el puntero de pila (ESP) delante de cada `module!functionname` línea.  
  
## <a name="remarks"></a>Comentarios  
 El `_EFN_StackTrace` estructura puede llamarse desde una interfaz de programación WinDbg. Se usan los siguientes parámetros:  
  
-   Si `wszTextOut` es null y `puiTextLength` es no es null, la función devuelve la longitud de cadena en `puiTextLength`.  
  
-   Si `wszTextOut` es no es null, la función almacena el texto en `wszTextOut` hasta la ubicación indicada por `puiTextLength`. Devuelve un resultado correctamente si había espacio suficiente en el búfer, o devuelve E_OUTOFMEMORY si el búfer no es suficientemente larga.  
  
-   Se omite la parte de la transición de la función si `pTransitionContexts` y `puiTransitionContextCount` son null. En este caso, la función proporciona a los llamadores con salida de texto de sólo los nombres de función.  
  
-   Si `pTransitionContexts` es null y `puiTransitionContextCount` es no es null, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount`.  
  
-   Si `pTransitionContexts` es no es null, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount`. El tamaño de la estructura es proporcionado por `uiSizeOfContext`, y debe tener el tamaño de [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` para la arquitectura.  
  
-   `wszTextOut`se escribe en el formato siguiente:  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   Si el desplazamiento en hexadecimal es 0 x 0, no se escribe ningún desplazamiento.  
  
-   Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.  
  
-   El `Flags` parámetro es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada `module!functionname` línea. De forma predeterminada, es 0.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
