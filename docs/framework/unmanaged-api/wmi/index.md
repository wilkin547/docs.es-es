---
title: WMI y contadores de rendimiento (referencia de API no administrada)
description: "Resume el .NET Framework API no administrada para obtener información de contador de rendimiento y WMI."
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.date: 11/06/2017
ms.topic: article-type-from-white-list
ms.prod: .net-framework
ms.devlang: cpp
ms.openlocfilehash: 461d90aaf5beca1c0f1d1965ce0ea07411e56e79
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Instrumental de administración de Windows (WMI) y los contadores de rendimiento (referencia de API no administrada)

La API no administrada de .NET Framework WMI y contadores de rendimiento se compone de un conjunto de funciones que encapsulan llamadas a la [API de Instrumental de administración de Windows nativo](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx). Permite desarrollar herramientas y bibliotecas que administración y supervisar los sistemas de equipo remoto.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
La API incluye las siguientes funciones:

| Función | Descripción |
|---------|---------|
| [BeginEnumeration (función)](beginenumeration.md) | Restablece el enumerador al principio de una enumeración de propiedades del objeto WMI. |
| [BeginMethodEnumeration (función)](beginmethodenumeration.md) |  Comienza una enumeración de los métodos disponibles para un objeto. |
| [BlessIWbemServices (función)](blessiwbemservices.md) | Indica si las credenciales de usuario permiten el acceso a una clase IWbemServices especificada. |
| [BlessIWbemServicesObject (función)](blessiwbemservicesobject.md) | Indica si las credenciales de usuario permiten el acceso a un objeto de servicio IWbem especificado. |
| [Clone (función)](clone.md) | Devuelve un nuevo objeto que es un clon completo del objeto actual. |
| [CloneEnumWbemClassObject (función)](cloneenumwbemclassobject.md) | Realiza una copia lógica de un enumerador, conserva su posición actual en una enumeración. |
| [CompareTo (función)](compareto.md) | Compara un objeto con otro objeto de administración de Windows. |
| [ConnectServerWmi (función)](connectserverwmi.md) | Crea una conexión a través de DCOM a un espacio de nombres WMI en un equipo especificado. |
| [CreateClassEnumWmi (función)](createclassenumwmi.md) | Devuelve un enumerador para todas las clases que cumplen los criterios de selección especificado. |
| [CreateInstanceEnumWmi (función)](createinstanceenumwmi.md) | Devuelve un enumerador que devuelve el aceptadas de una clase especificada que cumplen los criterios de selección especificados. |
| [Eliminar (función)](delete.md) | Elimina una propiedad especificada de una definición de clase y todos sus calificadores. |
| [DeleteMethod (función)](deletemethod.md) | Elimina un método especificado de una definición de clase CIM. |
| [EndEnumeration (función)](endenumeration.md) | Finaliza una secuencia de enumeración. | 
| [EndMethodEnumeration (función)](endmethodenumeration.md) | Finaliza una secuencia de enumeración iniciada mediante la llamada la [BeginMethodEnumeration función](beginmethodenumeration.md). |
| [ExecNotificationQueryWmi (función)](execnotificationquerywmi.md) | Ejecuta una consulta para recibir eventos. |
| [ExecQueryWmi (función)](execquerywmi.md) | Ejecuta una consulta para recuperar los objetos. |
| [FormatFromRawValue (función)](formatfromrawvalue.md) | Convierte un valor de datos de rendimiento sin procesar en el formato especificado, o dos valores de datos de rendimiento sin procesar si la conversión de formato se basa en el tiempo. | 
| [Get (función)](get.md) | Recupera un valor de propiedad especificado, si existe. |
| [GetCurrentApartmentType (función)](getcurrentapartmenttype.md) | Recupera el tipo de contenedor en el que se está ejecutando el llamador. |
| [GetDemultiplexedStub (función)](getdemultiplexedstub.md) | Crea un receptor de reenviador de objeto para ayudar a un cliente recibir las llamadas asincrónicas de administración de Windows. |
| [GetErrorInfo (función)](geterrorinfo.md) | Recupera información de error de la llamada de función anterior. | 
| [GetMethod (función)](getmethod.md) | Recupera información sobre el método especificado. | 
| [GetMethodOrigin (función)](getmethodorigin.md) | Determina la clase en la que se declara un método. |
| [GetMethodQualifierSet (función)](getmethodqualifierset.md) | Recupera el calificador establecido para un método concreto. |
| [GetNames (función)](getnames.md) | Recupera un subconjunto o todos los nombres de las propiedades de un objeto. |
| [GetObjectText (función)](getobjecttext.md) | Devuelve una representación textual de un objeto en la sintaxis MOF. | 
| [GetPropertyHandle (función)](getpropertyhandle.md) | Devuelve un identificador único que identifica una propiedad. |
| [GetPropertyOrigin (función)](getpropertyorigin.md) | Determina la clase en la que se declara una propiedad. |
| [GetPropertyQualifierSet (función)](getpropertyqualifierset.md) | Recupera el calificador establecido para una propiedad determinada.  |
| [GetQualifierSet (función)](getqualifierset.md) | Recupera el calificador establecido para una instancia de clase o una definición de clase. |
| [InheritsFrom (función)](inheritsfrom.md) | Determina si la instancia o clase actual se deriva de una clase principal especificada. |
| [Initialize (función)](initialize.md) | Realiza la inicialización de WMI. |
| [Función siguiente](next.md) | Recupera la siguiente propiedad en una enumeración. | 
| [NextMethod (función)](nextmethod.md) | Recupera el método siguiente en una enumeración. |
| [Función Put](put.md) | Establece una propiedad con nombre en un nuevo valor. |
| [PutClassWmi (función)](putclasswmi.md) | Crea una nueva clase o actualiza uno existente. |
| [PutInstanceWmi (función)](putinstancewmi.md) | Crea o actualiza una instancia de una clase existente. La instancia se escribe en el repositorio de WMI. |
| [PutMethod (función)](putmethod.md) | Crea un método. |
| [QualifierSet_BeginEnumeration (función)](qualifierset-beginenumeration.md) | Restablece el enumerador de los calificadores de un objeto al principio de la enumeración. |
| [QualifierSet_Delete (función)](qualifierset-delete.md) | Elimina un calificador especificado por su nombre.  |
| [QualifierSet_EndEnumeration (función)](qualifierset-endenumeration.md) | Finaliza la enumeración iniciada con una llamada a la `QualifierSet_BeginEnumeration` (función). |
| [QualifierSet_Get (función)](qualifierset-get.md) | Obtiene el calificador con nombre especificado.  |
| [QualifierSet_GetNames (función)](qualifierset-getnames.md) | Recupera los nombres de todos los calificadores o de calificadores especificados que están disponibles en el objeto actual o la propiedad. |
| [QualifierSet_Next (función)](qualifierset-next.md) | Recupera el siguiente calificador en una enumeración que se inició con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (función). |
| [QualifierSet_Put (función)](qualifierset-put.md) | Escribe el valor y calificador con nombre. |
| [ResetSecurity (función)](resetsecurity.md) | Asigna el token de suplantación proporcionado para el subproceso actual. |
| [SetSecurity (función)](setsecurity.md) | Recupera el token de suplantación asociado con el subproceso actual. |
| [SpawnDerivedClass (función)](spawnderivedclass.md) | Crea un objeto de clase recién derivada de un objeto especificado. | 
| [Función SpawnInstance](spawninstance.md) | Crea una nueva instancia de una clase. |   
| [VerifyClient (función)](verifyclientkey.md) | Garantiza que la clave de cliente tiene la seguridad correcta. |
| [WritePropertyValue (función)](writepropertyvalue.md) | Escribe un número especificado de bytes en una propiedad identificada por un identificador de propiedad. |

 ## <a name="see-also"></a>Vea también
[Referencia de API no administrada](../index.md) 