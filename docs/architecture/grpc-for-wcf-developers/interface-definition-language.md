---
title: 'Lenguaje de definición de interfaz: gRPC para desarrolladores de WCF'
description: Introducción a los búferes de protocolo IDL.
ms.date: 09/02/2019
ms.openlocfilehash: 841f041ae350e76e648c71f9d6d113b9d39e0d3b
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543214"
---
# <a name="interface-definition-language"></a>Lenguaje de definición de interfaz

Con Windows Communication Foundation (WCF), los servicios pueden exponer metadatos de Descripción mediante el lenguaje de definición de servicios web (WSDL). WSDL se genera dinámicamente mediante la reflexión de .NET en tiempo de ejecución. Los desarrolladores pueden usar estos metadatos para generar clientes para esos servicios, potencialmente en otros lenguajes si usan un enlace de plataforma independiente como SOAP sobre HTTP.

gRPC usa el lenguaje de definición de interfaz (IDL) de los búferes de protocolo. Los búferes de protocolo IDL son un lenguaje personalizado independiente de la plataforma con una especificación abierta. Los desarrolladores crean `.proto` archivos para describir los servicios, junto con sus entradas y salidas. Estos archivos de `.proto` se pueden usar para generar códigos auxiliares específicos de la plataforma o del idioma para clientes y servidores, lo que permite que varias plataformas diferentes se comuniquen. Al compartir archivos `.proto`, los equipos pueden generar código para usar los servicios de los demás, sin necesidad de realizar una dependencia del código.

Una de las ventajas de protobuf IDL es que, como un lenguaje personalizado, permite que gRPC sea completamente independiente del lenguaje y de la plataforma, sin favorecer ninguna tecnología sobre otra.

El IDL de protobuf también está diseñado para los usuarios de lectura y escritura, mientras que el WSDL está pensado como un formato legible/grabable de la máquina. Para cambiar el WSDL de un servicio WCF, normalmente es necesario cambiar el servicio, ejecutar el servicio y volver a generar el archivo WSDL desde el servidor. Por el contrario, con un archivo `.proto`, los cambios son sencillos de aplicar con un editor de texto y fluyen automáticamente a través del código generado. Visual Studio 2019 crea `.proto` archivos en segundo plano cuando se guardan. Con otros editores, como VS Code, los cambios se aplican cuando se compila el proyecto.

En comparación con XML y, en particular, con SOAP, los mensajes codificados con protobuf tienen muchas ventajas. Los mensajes protobuf suelen ser más pequeños que los mismos datos serializados como XML SOAP, y la codificación, la descodificación y la transmisión a través de una red pueden ser más rápidas.

La desventaja posible de protobuf en comparación con SOAP es que, dado que los mensajes no son legibles para los usuarios, se requiere herramientas adicionales para depurar el contenido del mensaje.

> [!TIP]
> gRPC *admite* la reflexión del servidor para tener acceso de forma dinámica a los servicios sin código auxiliar precompilado, aunque es más adecuado para las herramientas de uso general que los clientes específicos de la aplicación. Para obtener más información, consulte [GRPC Server Reflection Protocol](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) en github.

> [!NOTE]
> El formato binario de WCF, que se usa con el enlace NetTCP, es mucho más cercano a protobuf en cuanto a la compactación y el rendimiento. Pero NetTCP solo se puede usar entre clientes y servidores .NET, mientras que protobuf es una solución multiplataforma.

>[!div class="step-by-step"]
>[Anterior](approach.md)
>[Siguiente](network-protocols.md)
