---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 3cf3231bd48290c5b6b0ce8eeb6534de564c0c85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera la siguiente `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) estructuras en la lista del enumerador, devolverlas en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
  
 [in] Número de [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) se devuelven en estructuras `rgelt`.  
  
 `rgelt`  
  
 [out] Matriz de tamaño celt (o superior) para recibir estructuras RAWINPUTDEVICE enumeradas.  
  
 `pceltFetched`  
  
 [out] Puntero al número de elementos proporcionados realmente en `rgelt`. El llamador puede pasar `NULL` si `rgelt` es uno.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: S_OK si el número de elementos proporcionado es `celt`. En caso contrario, S_FALSE.
