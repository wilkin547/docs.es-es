---
title: LoadStringRC (Función)
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727554"
---
# <a name="loadstringrc-function"></a>LoadStringRC (Función)

Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `iResourceID`  
 [in] HRESULT.  
  
 `szBuffer`  
 enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.  
  
 `iMax`  
 de Tamaño del búfer del mensaje de error.  
  
 `bQuiet`  
 de Tendrán.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer` es null o `iMax` es cero (0).|  
  
## <a name="remarks"></a>Comentarios  

 Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll y Mscorwks.dll. Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [LoadStringRCEx (Función)](loadstringrcex-function.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
