---
title: WMI y contadores de rendimiento (referencia de API no administrada)
description: Resume la API no administrada de .NET Framework para WMI y la información sobre los contadores de rendimiento.
ms.date: 11/06/2017
ms.openlocfilehash: f28cd25ee6c3511dc5ac8a6dd4076c81f43fe74a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127421"
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Instrumental de administración de Windows (WMI) y contadores de rendimiento (referencia de API no administrada)

La API no administrada de la WMI y los contadores de rendimiento de .NET Framework consta de un conjunto de funciones que encapsulan llamadas a la [API nativa de Instrumental de administración de Windows](/windows/desktop/WmiSdk/com-api-for-wmi). Permite desarrollar herramientas y bibliotecas de administración y supervisión de los sistemas con equipos remotos.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

La API incluye estas funciones:

| Función | Description |
|---------|---------|
| [BeginEnumeration (función)](beginenumeration.md) | Restablece el enumerador al principio de una enumeración de propiedades del objeto de la WMI. |
| [BeginMethodEnumeration (función)](beginmethodenumeration.md) |  Comienza una enumeración de los métodos disponibles para un objeto. |
| [BlessIWbemServices (función)](blessiwbemservices.md) | Indica si las credenciales de usuario permiten acceder a una clase IWbemServices especificada. |
| [BlessIWbemServicesObject (función)](blessiwbemservicesobject.md) | Indica si las credenciales de usuario permiten acceder a un objeto de servicio IWbem especificado. |
| [Clone (función)](clone.md) | Devuelve un objeto nuevo que es un clon completo del objeto actual. |
| [CloneEnumWbemClassObject (función)](cloneenumwbemclassobject.md) | Realiza una copia lógica de un enumerador conservando su posición actual en una enumeración. |
| [CompareTo (función)](compareto.md) | Compara un objeto de administración de Windows con otro. |
| [Función ConnectServerWmi](connectserverwmi.md) | Crea una conexión a un espacio de nombres de WMI a través de DCOM en un equipo especificado. |
| [Función CreateClassEnumWmi](createclassenumwmi.md) | Devuelve un enumerador para todas las clases que cumplan los criterios de selección especificados. |
| [Función CreateInstanceEnumWmi](createinstanceenumwmi.md) | Devuelve un enumerador que devuelve las instancias de una clase especificada que cumpla los criterios de selección especificados. |
| [Delete (función)](delete.md) | Elimina una propiedad especificada de una definición de clase y todos sus calificadores. |
| [DeleteMethod (función)](deletemethod.md) | Elimina un método especificado de una definición de clase CIM. |
| [EndEnumeration (función)](endenumeration.md) | Finaliza una secuencia de enumeración. |
| [EndMethodEnumeration (función)](endmethodenumeration.md) | Finaliza una secuencia de enumeración iniciada mediante una llamada a la [función BeginMethodEnumeration](beginmethodenumeration.md). |
| [ExecNotificationQueryWmi (función)](execnotificationquerywmi.md) | Ejecuta una consulta para recibir eventos. |
| [ExecQueryWmi (función)](execquerywmi.md) | Ejecuta una consulta para recuperar objetos. |
| [FormatFromRawValue (función)](formatfromrawvalue.md) | Convierte un valor de datos de rendimiento sin procesar al formato especificado, o bien dos valores de datos de rendimiento sin procesar si la conversión de formato es de duración definida. |
| [Get (función)](get.md) | Recupera un valor de propiedad especificado si existe. |
| [Función GetCurrentApartmentType](getcurrentapartmenttype.md) | Recupera el tipo de contenedor en el que se está ejecutando el llamador. |
| [Función GetDemultiplexedStub](getdemultiplexedstub.md) | Crea un receptor de reenvío de objetos para ayudar a un cliente a recibir llamadas asincrónicas desde la administración de Windows. |
| [Función GetErrorInfo](geterrorinfo.md) | Recupera información sobre el error de la llamada de función anterior. |
| [GetMethod (función)](getmethod.md) | Recupera información sobre el método especificado. |
| [GetMethodOrigin (función)](getmethodorigin.md) | Determina la clase en la que se declara un método. |
| [GetMethodQualifierSet (función)](getmethodqualifierset.md) | Recupera el calificador establecido para un método específico. |
| [GetNames (función)](getnames.md) | Recupera un subconjunto o todos los nombres de las propiedades de un objeto. |
| [GetObjectText (función)](getobjecttext.md) | Devuelve una representación textual de un objeto usando la sintaxis MOF. |
| [GetPropertyHandle (función)](getpropertyhandle.md) | Devuelve un controlador único que identifica una propiedad. |
| [GetPropertyOrigin (función)](getpropertyorigin.md) | Determina la clase en la que se declara una propiedad. |
| [Función GetPropertyQualifierSet](getpropertyqualifierset.md) | Recupera el calificador establecido para una propiedad específica.  |
| [Función GetQualifierSet](getqualifierset.md) | Recupera el calificador establecido para una instancia o una definición de clase. |
| [Función InheritsFrom](inheritsfrom.md) | Determina si la clase o instancia actual deriva de una clase principal especificada. |
| [Inicializar función](initialize.md) | Realiza la inicialización de la WMI. |
| [Función Next](next.md) | Recupera la propiedad siguiente en una enumeración. |
| [Función NextMethod](nextmethod.md) | Recupera el método siguiente en una enumeración. |
| [Put (función)](put.md) | Establece una propiedad con nombre en un valor nuevo. |
| [Función PutClassWmi](putclasswmi.md) | Crea una imagen o actualiza una existente. |
| [Función PutInstanceWmi](putinstancewmi.md) | Crea o actualiza una instancia de una clase existente. La instancia se escribe en el repositorio de la WMI. |
| [Función PutMethod](putmethod.md) | Crea un método. |
| [Función QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) | Restablece un enumerador de los calificadores de un objeto al principio de la enumeración. |
| [Función QualifierSet_Delete](qualifierset-delete.md) | Elimina un calificador específico por el nombre.  |
| [Función QualifierSet_EndEnumeration](qualifierset-endenumeration.md) | Finaliza la enumeración iniciada con una llamada a la función `QualifierSet_BeginEnumeration`. |
| [Función QualifierSet_Get](qualifierset-get.md) | Obtiene el calificador con nombre especificado.  |
| [Función QualifierSet_GetNames](qualifierset-getnames.md) | Recupera los nombres de todos los calificadores o de aquellos especificados que están disponibles en el objeto o la propiedad actual. |
| [Función QualifierSet_Next](qualifierset-next.md) | Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
| [Función QualifierSet_Put](qualifierset-put.md) | Escribe el calificador y el valor con nombre. |
| [Función ResetSecurity](resetsecurity.md) | Asigna el token de suplantación proporcionado para el subproceso actual. |
| [Función SetSecurity](setsecurity.md) | Recupera el token de suplantación asociado al subproceso actual. |
| [Función SpawnDerivedClass](spawnderivedclass.md) | Crea un objeto de clase recién derivado a partir de un objeto específico. |
| [Función SpawnInstance](spawninstance.md) | Crea una instancia a partir de una clase. |
| [Función VerifyClient](verifyclientkey.md) | Garantiza que la clave de cliente cuenta con la seguridad adecuada. |
| [Función WritePropertyValue](writepropertyvalue.md) | Escribe un número específico de bytes en una propiedad identificada por un controlador de propiedad. |

## <a name="see-also"></a>Vea también

- [Referencia de API no administrada](../index.md)
