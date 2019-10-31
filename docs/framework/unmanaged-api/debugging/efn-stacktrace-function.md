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
ms.openlocfilehash: 272856c7eedbdc577158edcc463535a7946bb060
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122991"
---
# <a name="_efn_stacktrace-function"></a>\_EFN\_StackTrace (función)
Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Cliente que se está depurando.  
  
 `wszTextOut`  
 enuncia Representación de texto del seguimiento de la pila.  
  
 `puiTextLength`  
 enuncia Puntero al número de caracteres de `wszTextOut`.  
  
 `pTransitionContexts`  
 enuncia Matriz de contextos de transición.  
  
 `puiTransitionContextCount`  
 enuncia Puntero al número de contextos de transición de la matriz.  
  
 `uiSizeOfContext`  
 de Tamaño de la estructura de contexto.  
  
 `Flags`  
 de Se establece en 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) para mostrar el registro EBP y el puntero de pila Enter (ESP) delante de cada línea `module!functionname`.  
  
## <a name="remarks"></a>Comentarios  
 Se puede llamar a la estructura `_EFN_StackTrace` desde una interfaz de programación WinDbg. Los parámetros se utilizan de la siguiente manera:  
  
- Si `wszTextOut` es NULL y `puiTextLength` no es null, la función devuelve la longitud de la cadena en `puiTextLength`.  
  
- Si `wszTextOut` no es null, la función almacena el texto en `wszTextOut` hasta la ubicación indicada por `puiTextLength`. Devuelve correctamente si hay suficiente espacio en el búfer o devuelve E_OUTOFMEMORY si el búfer no era suficientemente largo.  
  
- La parte de la transición de la función se omite si `pTransitionContexts` y `puiTransitionContextCount` son NULL. En este caso, la función proporciona a los llamadores la salida de texto solo de los nombres de función.  
  
- Si `pTransitionContexts` es NULL y `puiTransitionContextCount` no es null, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount`.  
  
- Si `pTransitionContexts` no es null, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount`. `uiSizeOfContext`proporciona el tamaño de la estructura y debe ser el tamaño de [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` de la arquitectura.  
  
- `wszTextOut` se escribe en el formato siguiente:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Si el desplazamiento en Hex es 0X0, no se escribe ningún desplazamiento.  
  
- Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.  
  
- El parámetro `Flags` es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada línea `module!functionname`. De forma predeterminada, es 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
