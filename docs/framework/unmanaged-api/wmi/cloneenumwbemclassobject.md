---
title: "Función CloneEnumWbemClassObject (referencia de API no administrada)"
description: "La función de CloneEnumWbemClassObject realiza una copia lógica de un enumerador."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject (función)
Realiza una copia lógica de un enumerador, conserva su posición actual en una enumeración.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a>Parámetros

`ppEnum`  
[out] Recibe un puntero a una nueva [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).

`authLevel`  
[in] El nivel de autorización.

`impLevel`[in] El nivel de suplantación.

`pCurrentEnumWbemClassObject`  
[out] Un puntero a la [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instancia se va a clonar.

`strUser`   
[in] El nombre de usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`strPassword`   
[in] La contraseña. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`strAuthority`   
[in] El nombre de dominio del usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible completar la operación. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) método.

Este método realiza solo una copia de "mejor esfuerzo". Debido a la naturaleza dinámica de muchos objetos CIM, es posible que el nuevo enumerador no enumerar el mismo conjunto de objetos que el enumerador de origen.  

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
