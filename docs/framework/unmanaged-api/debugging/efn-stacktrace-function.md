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
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860735"
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
 de Establézcalo en 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) para mostrar el registro EBP y el puntero de pila Enter (ESP) delante de cada `module!functionname` línea.  
  
## <a name="remarks"></a>Comentarios  
 Se `_EFN_StackTrace` puede llamar a la estructura desde una interfaz de programación WinDbg. Los parámetros se utilizan de la siguiente manera:  
  
- Si `wszTextOut` es NULL y `puiTextLength` no es null, la función devuelve la longitud de la `puiTextLength`cadena en.  
  
- Si `wszTextOut` no es null, la función almacena el texto `wszTextOut` en la ubicación indicada por `puiTextLength`. Devuelve un valor correcto si hay suficiente espacio en el búfer o devuelve E_OUTOFMEMORY si el búfer no era suficientemente largo.  
  
- La parte de la transición de la función se `pTransitionContexts` omite `puiTransitionContextCount` si y son NULL. En este caso, la función proporciona a los llamadores la salida de texto solo de los nombres de función.  
  
- Si `pTransitionContexts` es NULL y `puiTransitionContextCount` no es null, la función devuelve el número necesario de entradas de contexto `puiTransitionContextCount`en.  
  
- Si `pTransitionContexts` no es null, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount`. Especifica `uiSizeOfContext`el tamaño de la estructura y debe ser el tamaño de [SimpleContext](stacktrace-simplecontext-structure.md) o `CONTEXT` de la arquitectura.  
  
- `wszTextOut`se escribe en el formato siguiente:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Si el desplazamiento en Hex es 0X0, no se escribe ningún desplazamiento.  
  
- Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.  
  
- El `Flags` parámetro es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada `module!functionname` línea. De forma predeterminada, es 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
