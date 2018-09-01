---
title: Función Next (referencia de API no administrada)
description: La siguiente función retireves la siguiente propiedad en una enumeración.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d470ccf9384695aa38a50c2c062c1b660fea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388619"
---
# <a name="next-function"></a>Función Next
Recupera la siguiente propiedad en una enumeración que comienza con una llamada a [BeginEnumeration](beginenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pstrName`  
[out] Un nuevo `BSTR` que contiene el nombre de propiedad. Puede establecer este parámetro en `null` si el nombre no es obligatorio.

`pVal`  
[out] Un `VARIANT` rellena con el valor de la propiedad. Puede establecer este parámetro en `null` si el valor no es obligatorio. Si la función devuelve un código de error, el `VARIANT` pasado a `pVal` es izquierda sin modificar. 

`pvtType`  
[out] Un puntero a un `CIMTYPE` variable (un `LONG` en que se coloca el tipo de la propiedad). El valor de esta propiedad puede ser un `VT_NULL_VARIANT`, en cuyo caso es necesario determinar el tipo real de la propiedad. Este parámetro también puede ser `null`. 

`plFlavor`  
[out] `null`, o un valor que recibe información sobre el origen de la propiedad. Consulte la sección [Nota] los valores posibles. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) función. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | El procedimiento remoto llamar comprendido entre el proceso actual y la administración de Windows no se pudo. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay ninguna propiedad más en la enumeración. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) método.

Este método también devuelve las propiedades del sistema.

Si el tipo subyacente de la propiedad es una ruta de acceso del objeto, una fecha o tiempo u otro tipo especial, el tipo devuelto no tiene suficiente información. El llamador debe examinar el `CIMTYPE` para la propiedad especificada determinar si la propiedad es una referencia de objeto, una fecha o tiempo u otro tipo especial.

Si `plFlavor` no `null`, el `LONG` valor recibe información acerca del origen de la propiedad, como se indica a continuación:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La propiedad es una propiedad estándar del sistema. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0 x 20 | Para una clase: la propiedad se hereda de la clase primaria. </br> Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Para una clase: la propiedad pertenece a la clase derivada. </br> Para una instancia: se ha modificado la propiedad por la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
