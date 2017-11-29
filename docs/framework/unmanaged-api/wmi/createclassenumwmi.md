---
title: "Función CreateClassEnumWmi (referencia de API no administrada)"
description: "La función CreateClassEnumWmi devuelve un enumerador para todas las clases que cumplen los criterios especificados."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbfee6f8e98d04a591c58560e6d50044e716a1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="createclassenumwmi-function"></a>CreateClassEnumWmi (función)
Devuelve un enumerador para todas las clases que cumplen los criterios de selección especificado.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>Parámetros

`strSuperclass`    
[in] Si no `null` o en blanco, especifica el nombre de una clase principal; el enumerador devuelve solo las subclases de esta clase. Si es `null` o en blanco y `lFlags` es WBEM_FLAG_SHALLOW, se devuelve solo clases de nivel superior (clases con ninguna clase de elemento primario). Si es `null` o en blanco y `lFlags` es `WBEM_FLAG_DEEP`, devuelve todas las clases del espacio de nombres.

`lFlags`   
[in] Una combinación de indicadores que afectan al comportamiento de esta función. Los valores siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código: 

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Si el conjunto, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual. <br/> Si no recupera de la función de conjunto, solo los calificadores que se almacenan en el espacio de nombres inmediato. |
| `WBEM_FLAG_DEEP` | 0 | La enumeración incluye todas las subclases de la jerarquía, pero no de esta clase. |
| `WBEM_FLAG_SHALLOW` | 1 | La enumeración incluye solo las instancias de esta clase puras y excluye todas las instancias de las subclases que proporcionan las propiedades que no se encuentran en esta clase. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | La marca hace una llamada semisincrónica. |
| `WBEM_FLAG_FORWARD_ONLY` | 0 x 20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de sólo avance son más rápidos y utilizan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI conserva punteros a objetos en el enumration hasta que se publican. | 

Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para mejorar el rendimiento.

`pCtx`  
[in] Normalmente, este valor es `null`. En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que proporciona las clases solicitadas. 

`ppEnum`  
[out] Recibe el puntero para el enumerador.

`authLevel`  
[in] El nivel de autorización.

`impLevel`[in] El nivel de suplantación.

`pCurrentNamespace`   
[in] Un puntero a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto que representa el espacio de nombres actual.

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
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función. |
| `WBEM_E_FAILED` | 0 x 80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | `strSuperClass` no existe. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI se ha detenido probablemente y reiniciar. Llame a [ConnectServerWmi](connectserverwmi.md) nuevo. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) método.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
