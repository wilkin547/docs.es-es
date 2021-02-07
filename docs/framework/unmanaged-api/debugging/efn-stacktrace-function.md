---
description: 'Más información acerca de: _EFN_StackTrace función'
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
ms.openlocfilehash: 6092d0793967cc422e30342783ab4dfd70b33de9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738291"
---
# <a name="_efn_stacktrace-function"></a>\_EFN \_ StackTrace (función)

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
 enuncia Puntero al número de caracteres de `wszTextOut` .  
  
 `pTransitionContexts`  
 enuncia Matriz de contextos de transición.  
  
 `puiTransitionContextCount`  
 enuncia Puntero al número de contextos de transición de la matriz.  
  
 `uiSizeOfContext`  
 de Tamaño de la estructura de contexto.  
  
 `Flags`  
 de Establézcalo en 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) para mostrar el registro EBP y el puntero de pila Enter (ESP) delante de cada `module!functionname` línea.  
  
## <a name="remarks"></a>Observaciones  

 `_EFN_StackTrace`Se puede llamar a la estructura desde una interfaz de programación WinDbg. Los parámetros se utilizan de la siguiente manera:  
  
- Si `wszTextOut` es NULL y `puiTextLength` no es null, la función devuelve la longitud de la cadena en `puiTextLength` .  
  
- Si `wszTextOut` no es null, la función almacena el texto en `wszTextOut` la ubicación indicada por `puiTextLength` . Devuelve un valor correcto si hay suficiente espacio en el búfer o devuelve E_OUTOFMEMORY si el búfer no era suficientemente largo.  
  
- La parte de la transición de la función se omite si `pTransitionContexts` y `puiTransitionContextCount` son NULL. En este caso, la función proporciona a los llamadores la salida de texto solo de los nombres de función.  
  
- Si `pTransitionContexts` es NULL y `puiTransitionContextCount` no es null, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount` .  
  
- Si `pTransitionContexts` no es null, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount` . Especifica el tamaño de la estructura `uiSizeOfContext` y debe ser el tamaño de [SimpleContext](stacktrace-simplecontext-structure.md) o `CONTEXT` de la arquitectura.  
  
- `wszTextOut` se escribe en el formato siguiente:  
  
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
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
