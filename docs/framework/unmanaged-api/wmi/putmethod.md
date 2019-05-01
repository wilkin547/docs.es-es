---
title: Función PutMethod (referencia de API no administrada)
description: La función PutMethod crea un método.
ms.date: 11/06/2017
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
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049263"
---
# <a name="putmethod-function"></a>Función PutMethod
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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`wszName`  
[in] El nombre del método que se va a crear. 

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pSignatureIn`  
[in] Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene el `in` parámetros del método. Este parámetro se omite si establece en `null`.  

`pSignatureOut`  
[in]  Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene el `out` parámetros del método. Este parámetro se omite si establece en `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | El `[in, out]` parámetro del método especificado en ambos el *pInSignature* y *pOutSignature* objetos tienen distintos calificadores.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Falta la especificación de un parámetro de método la **ID** calificador. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie de identificador que se asigna a los parámetros de método no es consecutiva o no empiezan en 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | El valor devuelto para un método tiene un **ID** calificador. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Se intentó reutilizar un nombre de método existente de una clase principal y las firmas no coincidían. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.

Esta llamada al método solo se admite si `ptr` es una definición de clase CIM. Manipulación de método no está disponible en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punteros que señalan a las instancias CIM.

Los usuarios no pueden crear métodos con nombres que empiezan o terminan con un carácter de subrayado. Esto está reservado para las propiedades y clases del sistema.

Para un método, el `in` y `out` se describen los parámetros como propiedades en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objetos.

Un `[in/out]` parámetros pueden definirse mediante la adición de la misma propiedad a ambos objetos al que apunta el `pInSignature` y `pOutSignature` parámetros. En este caso, las propiedades comparten el mismo **ID** valor del calificador.

Cada propiedad en un [__Parameters](/windows/desktop/WmiSdk/--parameters) distinto de la clase de objeto `ReturnValue` debe tener un **ID** calificador, un valor numérico de base cero que identifica el orden en que aparecen los parámetros. No hay dos parámetros pueden tener el mismo **ID** valor y no **ID** se puede omitir el valor. Si se produce alguna de estas condiciones, el `PutMethod` función devuelve `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
