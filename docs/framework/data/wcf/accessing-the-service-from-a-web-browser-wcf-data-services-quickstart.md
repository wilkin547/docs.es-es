---
title: Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)
description: Aprenda a iniciar WCF Data Services en Visual Studio y a deshabilitar la lectura de fuentes en un explorador. Obtiene el documento de definición de servicio y obtiene acceso a los recursos del servicio de datos.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247783"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)

Esta es la segunda tarea de la guía de inicio rápido de WCF Data Services. En esta tarea, iniciará el WCF Data Services desde Visual Studio y, opcionalmente, deshabilitará la lectura de fuentes en el explorador Web. A continuación, recupere el documento de definición de servicio, así como el acceso a los recursos del servicio de datos mediante el envío de solicitudes HTTP GET a través de un explorador Web a los recursos expuestos.

> [!NOTE]
> De forma predeterminada, Visual Studio asigna automáticamente un número de puerto al URI `localhost` en el equipo. En esta tarea se usa el número de puerto `12345` en los ejemplos de URI. Para obtener más información sobre cómo establecer un número de puerto específico en el proyecto de Visual Studio, vea [crear el servicio de datos](creating-the-data-service.md).

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>Para solicitar el documento de servicio predeterminado utilizando Internet Explorer

1. En Internet Explorer, en el menú **herramientas** , seleccione **Opciones de Internet**, haga clic en la pestaña **contenido** , haga clic en **configuración**y desactive **activar la visualización de fuentes**.

     De este modo, se garantiza que la lectura de fuentes queda deshabilitada. Si no deshabilita esta funcionalidad, el explorador web tratará el documento codificado como AtomPub devuelto como si fuera una fuente XML en lugar de mostrar los datos XML sin formato.

    > [!NOTE]
    > Si el explorador no puede mostrar la fuente como datos XML sin formato, todavía debería poder ver la fuente como el código fuente de la página.

2. En Visual Studio, presione la tecla **F5** para iniciar la depuración de la aplicación.

3. Abra un explorador web en el equipo local. En la barra de direcciones, escriba el siguiente URI:

    ```http
    http://localhost:12345/northwind.svc
    ```

     De esta forma, se devuelve el documento de servicio predeterminado, que contiene una lista de los conjuntos de entidades expuestos por este servicio de datos.

## <a name="to-access-entity-set-resources-from-a-web-browser"></a>Para tener acceso a los recursos del conjunto de entidades desde un explorador web

1. En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     Esto devuelve un conjunto de todos los clientes de la base de datos de ejemplo Northwind.

2. En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     De esta forma, se devuelve una instancia de la entidad para un cliente concreto, `ALFKI`.

3. En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     De esta forma, se recorre la relación entre clientes y pedidos para devolver un conjunto de todos los pedidos para ese cliente, `ALFKI`.

4. En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     De esta forma, se filtran los pedidos que pertenecen a un cliente determinado, `ALFKI`, de modo que solo se devuelve un pedido concreto dependiendo del valor proporcionado para `OrderID`.

## <a name="next-steps"></a>Pasos a seguir

Ha tenido acceso correctamente al WCF Data Services desde un explorador Web, con el explorador emitiendo solicitudes GET de HTTP a los recursos especificados. Un explorador web es un modo sencillo de experimentar con la sintaxis de direccionamiento de las solicitudes y de ver los resultados. Sin embargo, este método no se suele emplear para obtener acceso a un servicio de datos de producción. Habitualmente, las aplicaciones interactúan con el servicio de datos mediante el código de la aplicación o los lenguajes de script. A continuación, creará una aplicación cliente que usa las bibliotecas de cliente para tener acceso a los recursos del servicio de datos como si fueran objetos de Common Language Runtime (CLR):

> [!div class="nextstepaction"]
> [Creación de la aplicación cliente de .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vea también

- [Acceso a recursos de servicios de datos](accessing-data-service-resources-wcf-data-services.md)
