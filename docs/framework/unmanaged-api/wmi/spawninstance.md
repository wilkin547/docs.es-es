---
title: "Función SpawnInstance (referencia de API no administrada)"
description: "La función SpawnInstance crea una nueva instancia de una clase."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68508f3000e7f4ac481f940ef4c715366c37125c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="spawninstance-function"></a>Función SpawnInstance
Crea una nueva instancia de una clase.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewInstance`  
[out] Recibe el puntero a la nueva instancia de la clase. Si se produce un error, no es un nuevo objeto devuelto, y `ppNewInstance` es izquierda sin modificar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`no es una definición de clase válido y no se puede generar nuevas instancias. Está incompleto o no se ha registrado con la administración de Windows mediante una llamada a [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El valor de `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject:: SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) método.

`ptr`debe ser una definición de clase obtenida de la administración de Windows. (Tenga en cuenta que se admite la creación de una instancia de una instancia, pero la instancia devuelta está vacía). A continuación, utilizar esta definición de clase para crear nuevas instancias. Una llamada a la [PutInstanceWmi](putinstancewmi.md) función es necesaria si se va a escribir la instancia a la administración de Windows.




El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual. No se puede invalidar este comportamiento. No hay ningún otro método por el que se pueden crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
