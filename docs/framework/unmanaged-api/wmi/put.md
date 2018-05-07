---
title: Función Put (referencia de API no administrada)
description: La función Put asigna un nuevo valor a una propiedad con nombre.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f3ffe27bef6583b733fc04f2f25903d545daa74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="put-function"></a>Función Put
Establece una propiedad con nombre en un nuevo valor.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`wszName`  
[in] El nombre de la propiedad. Este parámetro no puede ser `null`.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pVal`   
[in] Un puntero a un válido `VARIANT` que se convierte en el nuevo valor de propiedad. Si `pVal` es `null` o apunta a un `VARIANT` de tipo `VT_NULL`, la propiedad se establece en `null`. 

`vtType`  
[in] El tipo de `VARIANT` señalada por `pVal`. Consulte la [comentarios](#remarks) sección para obtener más información.
 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Uno o más parámetros no son válidos. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | No se reconoce el tipo de propiedad. Este valor se devuelve cuando se crean instancias de clase si la clase ya existe. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_TYPE_MISMATCH` | 0 x 80041005 | Para instancias: indica que `pVal` apunta a un `VARIANT` de un tipo incorrecto para la propiedad. <br/> Para obtener definiciones de clase: la propiedad ya existe en la clase primaria y el nuevo tipo COM es diferente del tipo COM antiguo. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) método.

Esta función siempre sobrescribe el valor de propiedad actual por una nueva. Si el [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) apunta a una definición de clase `Put` crea o actualiza el valor de propiedad. Cuando [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) apunta a una instancia CIM, `Put` actualiza el valor de propiedad solo; `Put` no se puede crear un valor de propiedad.

El `__CLASS` propiedad del sistema resulta solo escritura durante la creación de la clase, no pueden dejarse en blanco. Todas las demás propiedades del sistema son de solo lectura.

Un usuario no puede crear propiedades con nombres que empezarán ni terminan con un carácter de subrayado ("_"). Se reserva para las propiedades y clases del sistema.

Si la propiedad se establece mediante el `Put` función existe en la clase primaria, el valor predeterminado de la propiedad se cambia a menos que el tipo de propiedad no coincide con el tipo de clase principal. Si la propiedad no existe y no es un tipo no coincidente, la propiedad es ceated.

Use la `vtType` parámetro solo cuando se crean nuevas propiedades en una definición de clase CIM y `pVal` es `null` o apunta a un `VARIANT` de tipo `VT_NULL`. En este caso, el `vType` parámetro especifica el tipo CIM de la propiedad. En los demás casos, `vtType` debe ser 0. `vtType` También debe ser 0 si el objeto subyacente es una instancia (aunque `Val` es `null`) porque el tipo de la propiedad es fijo y no se puede cambiar.   

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
