---
title: Función ExecQueryWmi (referencia de API no administrada)
description: La función ExecQueryWmi ejecuta una consulta para recuperar los objetos.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b482f2ca2e2d5c06e69945adb71aa6c0f5d26465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="execquerywmi-function"></a>ExecQueryWmi (función)
Ejecuta una consulta para recuperar los objetos.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

`strQueryLanguage`    
[in] Una cadena con el lenguaje de consulta válida compatible con la administración de Windows. Debe ser "WQL", que es el acrónimo de lenguaje de consulta de WMI.

`strQuery`  
[in] El texto de la consulta. Este parámetro no puede ser `null`.

`lFlags`   
[in] Una combinación de indicadores que afectan al comportamiento de esta función. Los valores siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código: 

| Constante | Valor  | Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Si el conjunto, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual. <br/> Si no recupera de la función de conjunto, solo los calificadores que se almacenan en el espacio de nombres inmediato. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | La marca hace una llamada semisincrónica. |
| `WBEM_FLAG_FORWARD_ONLY` | 0 x 20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de sólo avance son más rápidos y utilizan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI conserva punteros a objetos en el enumration hasta que se publican. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0 x 100 | Garantiza que cualquier devuelven objetos tienen suficiente información en ellos por lo que ese propiedades del sistema, como **__PATH**, **__RELPATH**, y **__SERVER**, no son `null`. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Esta marca se utiliza para la creación de prototipos. No se ejecuta la consulta y en su lugar, devuelve un objeto que es similar a un objeto de resultado típico. |
| `WBEM_FLAG_DIRECT_READ` | 0 x 200 | Causas acceso dirigen al proveedor para la clase especificada sin tener en cuenta su clase primaria o cualquier subclase. |

Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para mejorar el rendimiento.

`pCtx`  
[in] Normalmente, este valor es `null`. En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que proporciona las clases solicitadas. 

`ppEnum`  
[out] Si se produce ningún error, recibe el puntero para el enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta. La consulta puede tener un conjunto de resultados con cero instancias. Consulte la [comentarios](#remarks) sección para obtener más información.

`authLevel`  
[in] El nivel de autorización.

`impLevel` [in] El nivel de suplantación.

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
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | La consulta tenía un error de sintaxis. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | No se admite el lenguaje de consulta solicitado. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La consulta es demasiado compleja. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI se ha detenido probablemente y reiniciar. Llame a [ConnectServerWmi](connectserverwmi.md) nuevo. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La consulta especifica una clase que no existe. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) método.

Esta función procesa la consulta especificada en el `strQuery` parámetro y crea un enumerador a través del cual el autor de llamada puede tener acceso a los resultados de la consulta. El enumerador es un puntero a un [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interfaz; la consulta de resultados son instancias de objetos de clase disponibles a través de la [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interfaz.

No hay límite al número de `AND` y `OR` palabras clave que se puede usar en las consultas WQL. Gran número de palabras clave WQL usadas en una consulta compleja puede hacer WMI devolver el `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) código de error como un `HRESULT` valor. El límite de palabras clave WQL depende de su complejidad es de la consulta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
