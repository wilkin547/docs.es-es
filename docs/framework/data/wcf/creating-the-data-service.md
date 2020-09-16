---
title: Crear un servicio de datos de WCF en Visual Studio
description: Aprenda a crear un servicio de datos de ejemplo que usa WCF Data Services para exponer una fuente de OData basada en una base de datos de ejemplo.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: f6e95ce58e055f0c745b781c664309e4ef91ffc6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554018"
---
# <a name="create-the-data-service"></a>Crear el servicio de datos

En este tema, creará un servicio de datos de ejemplo que utiliza WCF Data Services para exponer una fuente Open Data Protocol (OData) basada en la base de datos de ejemplo Northwind. Esta tarea supone la realización de los siguientes pasos básicos:

1. Cree una aplicación web ASP.NET.

2. Defina el modelo de datos usando las herramientas de Entity Data Model.

3. Agregar el servicio de datos a la aplicación web.

4. Habilitar el acceso al servicio de datos.

## <a name="create-the-aspnet-web-app"></a>Creación de la aplicación Web de ASP.NET

1. En Visual Studio, en el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

1. En el cuadro de diálogo **nuevo proyecto** , en Visual Basic o Visual C#, seleccione la categoría **Web** y, a continuación, seleccione **aplicación Web ASP.net**.

1. Escriba `NorthwindService` como nombre del proyecto y seleccione **Aceptar**.

1. En el cuadro de diálogo **nueva aplicación Web de ASP.net** , seleccione **vacío** y, después, haga clic en **Aceptar**.

1. (Opcional) Especifique un número de puerto específico para la aplicación web. Nota: el número de puerto `12345` se usa en esta serie de temas de inicio rápido.

    1. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net que acaba de crear y, a continuación, elija **propiedades**.

    2. Seleccione la pestaña **Web** y establezca el valor del cuadro de texto **puerto específico** en `12345` .

## <a name="define-the-data-model"></a>Definir el modelo de datos

1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.

3. Como nombre del modelo de datos, escriba `Northwind.edmx` .

4. En el **Asistente para Entity Data Model**, seleccione **EF Designer desde base de datos**y, a continuación, haga clic en **siguiente**.

5. Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:

    - Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y cree una conexión nueva. Para obtener más información, consulta [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.

         \- o -

    - Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.

6. En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.

7. Haga clic en **Finalizar** para cerrar el asistente.

## <a name="create-the-wcf-data-service"></a>Crear el servicio de datos de WCF

1. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net y, a continuación, elija **Agregar**  >  **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla de elemento de **servicio de datos de WCF** en la categoría **Web** .

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.

3. Como nombre del servicio, escriba `Northwind` .

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código. En **Explorador de soluciones**, el servicio tiene el nombre Northwind con la extensión *. SVC.CS* o *. SVC. VB*.

4. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`. La definición de la clase debería ser como la siguiente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Habilitar el acceso a los recursos del servicio de datos

1. En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     De esta forma, los clientes autorizados pueden tener acceso de lectura y escritura a los recursos para los conjuntos de entidades especificados.

    > [!NOTE]
    > Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos. En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos también debería proteger la aplicación. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).

## <a name="next-steps"></a>Pasos siguientes

Ha creado correctamente un nuevo servicio de datos que expone una fuente de OData basada en la base de datos de ejemplo Northwind y ha habilitado el acceso a la fuente para los clientes que tienen permisos en la aplicación Web ASP.NET. A continuación, iniciará el servicio de datos desde Visual Studio y tendrá acceso a la fuente de OData mediante el envío de solicitudes HTTP GET a través de un explorador Web:

> [!div class="nextstepaction"]
> [Acceder al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vea también

- [ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
