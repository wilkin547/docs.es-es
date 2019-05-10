---
title: Crear un servicio de datos WCF en Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: d23df38d479cb8f29f3e49225e96552ccdb84645
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641135"
---
# <a name="create-the-data-service"></a>Crear el servicio de datos

En este tema, creará un servicio de datos de ejemplo que usa WCF Data Services para exponer un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente que se basa en la base de datos de ejemplo Northwind. Esta tarea supone la realización de los siguientes pasos básicos:

1. Cree una aplicación web ASP.NET.

2. Defina el modelo de datos usando las herramientas de Entity Data Model.

3. Agregar el servicio de datos a la aplicación web.

4. Habilitar el acceso al servicio de datos.

## <a name="create-the-aspnet-web-app"></a>Crear la aplicación web ASP.NET

1. En Visual Studio, en el **archivo** menú, seleccione **New** > **proyecto**.

1. En el **nuevo proyecto** cuadro de diálogo, en Visual Basic o Visual C#, seleccione el **Web** categoría y, a continuación, seleccione **aplicación Web ASP.NET**.

1. Escriba `NorthwindService` como el nombre del proyecto y, a continuación, seleccione **Aceptar**.

1. En el **nueva aplicación Web ASP.NET** cuadro de diálogo, seleccione **vacía** y, a continuación, seleccione **Aceptar**.

1. (Opcional) Especifique un número de puerto específico para la aplicación web. Nota: el número de puerto `12345` se usa en esta serie de tutoriales rápidos.

    1. En **el Explorador de soluciones**, haga doble clic en el proyecto ASP.NET que acaba de crear y, a continuación, elija **propiedades**.

    2. Seleccione el **Web** pestaña y establezca el valor de la **puerto específico** cuadro de texto para `12345`.

## <a name="define-the-data-model"></a>Definir el modelo de datos

1. En **el Explorador de soluciones**, haga clic en el nombre del proyecto ASP.NET y, a continuación, haga clic en **agregar** > **nuevo elemento**.

2. En el **Agregar nuevo elemento** cuadro de diálogo, seleccione el **datos** categoría y, a continuación, seleccione **ADO.NET Entity Data Model**.

3. Para el nombre del modelo de datos, escriba `Northwind.edmx`.

4. En el **Asistente para Entity Data Model**, seleccione **EF Designer de base de datos**y, a continuación, haga clic en **siguiente**.

5. Conectar el modelo de datos a la base de datos, realice uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:

    - Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y crear una nueva conexión. Para obtener más información, vea [Cómo: Crear conexiones a bases de datos SQL Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.

         \- o -

    - Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.

6. En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.

7. Haga clic en **finalizar** para cerrar el asistente.

## <a name="create-the-wcf-data-service"></a>Crear el servicio de datos WCF

1. En **el Explorador de soluciones**, haga doble clic en el proyecto ASP.NET y, a continuación, elija **agregar** > **nuevo elemento**.

2. En el **Agregar nuevo elemento** cuadro de diálogo, seleccione el **WCF Data Service** plantilla de elemento desde el **Web** categoría.

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > El **WCF Data Service** plantilla está disponible en Visual Studio 2015, pero no en Visual Studio 2017.

3. El nombre del servicio, escriba `Northwind`.

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código. En **el Explorador de soluciones**, el servicio tiene el nombre Northwind con la extensión *. svc.cs* o *. svc.vb*.

4. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`. La definición de la clase debería ser como la siguiente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Habilitar el acceso a los recursos de servicio de datos

1. En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     De esta forma, los clientes autorizados pueden tener acceso de lectura y escritura a los recursos para los conjuntos de entidades especificados.

    > [!NOTE]
    > Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos. En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos también debería proteger la aplicación. Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

## <a name="next-steps"></a>Pasos siguientes

Ha creado correctamente un nuevo servicio de datos que expone una fuente de OData que se basa en la base de datos de ejemplo Northwind y ha habilitado el acceso a la fuente para los clientes que tienen permisos en la aplicación Web ASP.NET. A continuación, deberá iniciar el servicio de datos desde Visual Studio y tener acceso a la fuente enviando solicitudes GET de HTTP a través de un explorador Web OData:

> [!div class="nextstepaction"]
> [Tener acceso al servicio desde un explorador web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vea también

- [Herramientas de ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))