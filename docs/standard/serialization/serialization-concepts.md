---
title: Conceptos de serialización
ms.date: 08/07/2017
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
ms.openlocfilehash: 1a7fa7c3e5561fc9e48cf627a703abc747a72ba0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159837"
---
# <a name="serialization-concepts"></a>Conceptos de serialización
¿Por qué desearía utilizar la serialización? Las dos razones más importantes son conservar así el estado de un objeto a los medios de almacenamiento, de manera que una copia exacta se puede recrear en una copia intermedia posterior y para enviar por valor el objeto de un dominio de aplicación a otro. Por ejemplo, la serialización se utiliza para guardar el estado de sesión en ASP.NET y copiar los objetos en el Portapapeles en Windows Forms. La comunicación remota se utiliza también para pasar por valor los objetos de un dominio de aplicación a otro.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="persistent-storage"></a>Almacenamiento persistente
Es a menudo necesario almacenar el valor de los campos de un objeto en el disco y a continuación, más tarde, recuperar estos datos. Aunque esto es fácil de lograr sin confiar en la serialización, este enfoque es a menudo embarazoso y propenso a errores y se vuelve progresivamente más complejo al necesitar realizar el seguimiento de una jerarquía de objetos. Imagine escribir una aplicación empresarial grande, que contiene miles de objetos, y tener que escribir el código para guardar y restaurar los campos y propiedades a y desde el disco para cada objeto. La serialización proporciona un mecanismo conveniente para lograr este objetivo.

Common Language Runtime administra cómo se almacenan los objetos en memoria y proporciona un mecanismo de serialización automatizado mediante [reflexión](../../../docs/framework/reflection-and-codedom/reflection.md). Cuando se serializa un objeto, el nombre de la clase, el ensamblado y todos los miembros de datos de la instancia de clase se escribe en el almacenamiento. Los objetos almacenan a menudo referencias a otras instancias en variables miembro. Cuando se serializa la clase, las pistas de motor de serialización hacen referencia a los objetos, ya serializados, para asegurarse de que no se serializa el mismo objeto más de una vez. La arquitectura de serialización proporcionada con el .NET Framework controla correctamente los gráficos de objetos y las referencias circulares automáticamente. El único requisito de los gráficos de objetos es que todos los objetos, a los que hace referencia el objeto serializado, también se deben marcar como `Serializable` (para más información, vea [Serialización básica](basic-serialization.md)). Si no se hace esto, se producirá una excepción cuando el serializador intente serializar el objeto sin marca.

Cuando se deserializa la clase serializada, se vuelve a crear la clase y se restauran automáticamente los valores de todos los miembros de datos.

## <a name="marshal-by-value"></a>Serializar por valor
Los objetos sólo son válidos en el dominio de aplicación donde se crean. Se produce un error ante cualquier intento de pasar el objeto como un parámetro o de devolverlo como un resultado, a menos que el objeto derive de `MarshalByRefObject` o esté marcado como `Serializable`. Si el objeto está marcado como `Serializable`, se serializa automáticamente, se transporta de un dominio de aplicación al otro y luego se deserializa para generar una copia exacta del objeto en el segundo dominio de aplicación. Este proceso se conoce normalmente como valor por cálculo de referencias.

Cuando un objeto deriva de `MarshalByRefObject`, se pasa una referencia al objeto de un dominio de aplicación a otro, en lugar de pasar el propio objeto. También puede marcar un objeto que derive de `MarshalByRefObject` como `Serializable`. Cuando se usa este objeto con comunicación remota, el formateador responsable de la serialización, que se ha preconfigurado con un selector suplente (`SurrogateSelector`), toma el control del proceso de serialización y reemplaza todos los objetos derivados de `MarshalByRefObject` por un proxy. Sin `SurrogateSelector`, la arquitectura de serialización sigue las reglas de serialización estándar descritas en [Pasos del proceso de serialización](steps-in-the-serialization-process.md).  

## <a name="related-sections"></a>Secciones relacionadas  
 [Serialización binaria](../../../docs/standard/serialization/binary-serialization.md)  
 Describe el mecanismo de la serialización binaria que está incluido con Common Language Runtime.  
  
 \ [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
 Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.  
  
 [Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 Describe el mecanismo de la serialización XML y SOAP que está incluido con Common Language Runtime.
