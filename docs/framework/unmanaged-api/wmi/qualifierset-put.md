---
title: Función QualifierSet_Put (referencia de API no administrada)
description: La función QualifierSet_Put escribe el calificador con nombre y su valor.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf3d422bbcec2754601f6dd07d7b45bab2a716e3
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201188"
---
# <a name="qualifiersetput-function"></a>Función QualifierSet_Put
Escribe el calificador y el valor con nombre. El nuevo calificador sobrescribe el valor anterior del mismo nombre. Si el calificador no existe, se crea. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`   
[in] Este parámetro se usa.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`wszName`   
[in] El nombre del calificador que se va a escribir.

`pVal` [in] Un puntero a una `VARIANT` que contiene el calificador a escribir. Este parámetro no puede ser `null`.

`lFlavor` [in] Una de las constantes siguientes que define los tipos de calificador deseado para este calificador. El valor predeterminado es `WBEM_FLAVOR_OVERRIDABLE` (0).

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | El calificador se puede invalidar en una clase derivada o una instancia. **Este es el valor predeterminado.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | El calificador se propaga a las instancias. |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | El calificador se propaga a las clases derivadas. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | El calificador no puede invalidarse en una clase o instancia derivada. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | El calificador está localizado. |

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Se produjo un intento no válido para especificar el **clave** calificador en una propiedad que no puede ser una clave. Las claves se especifican om c; la definición de clase para un objeto y no se pueden modificar por instancia. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | El `pVal` parámetro no es de un tipo de calificador válido. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | No es posible llamar a la `QualifierSet_Put` invalida el método en el calificador porque el objeto propietario no permite. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
