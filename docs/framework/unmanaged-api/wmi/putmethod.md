---
title: "Función PutMethod (referencia de API no administrada)"
description: "La función PutMethod crea un método."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a>PutMethod (función)
Crea un método.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`wszName`  
[in] El nombre del método que se va a crear. 

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pSignatureIn`  
[in] Un puntero a una copia de la [clase del sistema __Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) que contiene el `in` parámetros para el método. Este parámetro se ignora si establece en `null`.  

`pSignatureOut`  
[in]  Un puntero a una copia de la [clase del sistema __Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) que contiene el `out` parámetros para el método. Este parámetro se ignora si establece en `null`.
 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Uno o más parámetros no son válidos. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | El `[in, out]` parámetro del método especificada tanto en el *pInSignature* y *pOutSignature* objetos tienen calificadores diferentes.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Falta la especificación de un parámetro de método la **identificador** calificador. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie de identificador que se asigna a los parámetros de método no es consecutiva o no se inicia en 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | El valor devuelto para un método tiene un **identificador** calificador. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Se intentó volver a usar un nombre de método existente de una clase principal y no coincidía con las firmas. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) método.

Llamar a este método solo se admite si `ptr` es una definición de clase CIM. Manipulación de método no está disponible en [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) punteros que señalan a las instancias CIM.

Los usuarios no pueden crear métodos cuyos nombres comienzan ni terminan con un carácter de subrayado. Se reserva para las propiedades y clases del sistema.

Para un método, el `in` y `out` parámetros se describen como propiedades en [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objetos.

Un `[in/out]` los parámetros pueden definirse mediante la adición de la misma propiedad a los dos objetos que señala el `pInSignature` y `pOutSignature` parámetros. En este caso, las propiedades comparten la misma **identificador** valor del calificador.

Cada propiedad en un [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) distinto de la clase de objeto `ReturnValue` debe tener un **identificador** calificador, un valor numérico de base cero que identifica el orden en que aparecen los parámetros. No hay dos parámetros pueden tener el mismo **Id. de** valor y no **identificador** se puede omitir el valor. Si se produce alguna de estas condiciones, el `PutMethod` función devuelve `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
