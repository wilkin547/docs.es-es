---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 329a2cd96346e199ee834856dd6dbfac6175b722
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515322"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera las siguientes `celt` [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) estructuras en la lista del enumerador, devolverlos en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
  
 [in] Número de [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) se devuelven en estructuras `rgelt`.  
  
 `rgelt`  
  
 [out] Matriz de tamaño celt (o superior) para recibir estructuras RAWINPUTDEVICE enumeradas.  
  
 `pceltFetched`  
  
 [out] Puntero al número de elementos proporcionados realmente en `rgelt`. El llamador puede pasar `NULL` si `rgelt` es uno.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: S_OK si el número de elementos proporcionado es `celt`. En caso contrario, S_FALSE.
