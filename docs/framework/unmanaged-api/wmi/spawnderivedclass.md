---
title: "Función SpawnDerivedClass (referencia de API no administrada)"
description: "La función SpawnDerivedClass crea un nuevo objeto que se deriva de un objeto."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 51a0dd0013b1bb3898bcc81ee2d64be20a5b6ecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass (función)
Crea un objeto de clase recién derivada de un objeto especificado.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewClass`  
[out] Recibe el puntero al nuevo objeto de definición de clase. Si se produce un error, no es un nuevo objeto devuelto, y `ppNewClass` es izquierda sin modificar. Su valor no puede ser `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Se solicitó una operación no válida, como la creación de una clase a partir de una instancia. |
| `WBEM_E_INCOMPLETE_CLASS` | La clase de origen no está completamente definida o registrada con la administración de Windows, por lo que no se permite una nueva clase derivada. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El valor de `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) método.

`ptr`debe ser una definición de clase que se convierte en la clase primaria del objeto generado. El objeto devuelto se convierte en una subclase del objeto actual.

El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual. No se puede invalidar este comportamiento. No hay ningún otro método por el que se pueden crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
