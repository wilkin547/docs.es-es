---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053398"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera las siguientes `celt` estructuras [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) en la lista del enumerador `rgelt` y las devuelve junto con el número real de elementos enumerados en. `pceltFetched`  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
  
 de Número de estructuras [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) devueltas en `rgelt`.  
  
 `rgelt`  
  
 [out] Matriz de tamaño celt (o superior) para recibir estructuras RAWINPUTDEVICE enumeradas.  
  
 `pceltFetched`  
  
 [out] Puntero al número de elementos proporcionados realmente en `rgelt`. El llamador puede pasar `NULL` si `rgelt` es uno.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: S_OK si el número de elementos proporcionado es `celt`; S_FALSE en caso contrario.
