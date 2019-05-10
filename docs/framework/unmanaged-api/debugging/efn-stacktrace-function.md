---
title: _EFN_StackTrace (Función)
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0074584ee5baba358db5bf3b0f2cfdd9a3d8f1d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593538"
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
  
## <a name="parameters"></a>Parámetros  
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
 [in] Se establece en 0 o SOS_STACKTRACE_SHOWADDRESSES (0 x 01) para mostrar el registro EBP y el puntero de pila (ESP) delante de cada `module!functionname` línea.  
  
## <a name="remarks"></a>Comentarios  
 El `_EFN_StackTrace` estructura puede llamarse desde una interfaz de programación WinDbg. Los parámetros se usan como sigue:  
  
- Si `wszTextOut` es null y `puiTextLength` es no nulo, la función devuelve la longitud de cadena en `puiTextLength`.  
  
- Si `wszTextOut` es no nulo, la función almacena el texto en `wszTextOut` hasta la ubicación indicada por `puiTextLength`. Devuelve correctamente si había espacio suficiente en el búfer, o se devuelve E_OUTOFMEMORY si el búfer no es suficientemente larga.  
  
- La parte de la transición de la función se omite si `pTransitionContexts` y `puiTransitionContextCount` ambos son null. En este caso, la función proporciona a los llamadores con salida de texto de sólo los nombres de función.  
  
- Si `pTransitionContexts` es null y `puiTransitionContextCount` es no nulo, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount`.  
  
- Si `pTransitionContexts` es no nulo, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount`. El tamaño de la estructura viene dado por `uiSizeOfContext`, y debe ser el tamaño de [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` para la arquitectura.  
  
- `wszTextOut` se escribe en el formato siguiente:  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Si el desplazamiento en hexadecimal 0 x 0, no se escribe ningún desplazamiento.  
  
- Si no hay ningún código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.  
  
- El `Flags` parámetro es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada `module!functionname` línea. De forma predeterminada, es 0.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: SOS_Stacktrace.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
