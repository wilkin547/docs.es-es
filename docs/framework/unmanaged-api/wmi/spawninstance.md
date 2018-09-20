---
title: Función SpawnInstance (referencia de API no administrada)
description: La función SpawnInstance crea una nueva instancia de una clase.
ms.date: 11/06/2017
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
ms.openlocfilehash: fb187719ff502abe61ac5deb69c6427a4a64ab44
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321384"
---
# <a name="spawninstance-function"></a>Función SpawnInstance
Crea una instancia a partir de una clase.    
  
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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewInstance`  
[out] Recibe el puntero a la nueva instancia de la clase. Si se produce un error, no es un nuevo objeto devuelto, y `ppNewInstance` es izquierda sin modificar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` no es una definición de clase válido y no se puede generar nuevas instancias. Es incompleto o no se registró con la administración de Windows mediante una llamada a [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El valor de `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) método.

`ptr` debe ser una definición de clase obtenida de la administración de Windows. (Tenga en cuenta que al generar una instancia de una instancia es compatible, pero la instancia devuelta está vacía). Utilizamos esta definición de clase para crear nuevas instancias. Una llamada a la [PutInstanceWmi](putinstancewmi.md) función es necesaria si va a escribir la instancia a la administración de Windows.




El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual. No se puede invalidar este comportamiento. No hay ningún otro método que se pueden crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
