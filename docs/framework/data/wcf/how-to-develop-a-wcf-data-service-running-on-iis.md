---
description: 'Más información acerca de cómo: desarrollar un servicio de datos de WCF que se ejecuta en IIS'
title: Procedimiento para desarrollar un servicio de datos WCF que se ejecuta en IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: b4d7b322a00e3c9c43005a416c608e1b98f1ce51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765482"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Cómo: desarrollar un servicio de datos de WCF que se ejecuta en IIS

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

En este artículo se muestra cómo usar Servicios de datos de WCF para crear un servicio de datos basado en la base de datos de ejemplo Northwind hospedada por una aplicación Web de ASP.NET que se ejecuta en Internet Information Services (IIS). Para ver un ejemplo de cómo crear el mismo servicio de datos de Northwind como una aplicación Web de ASP.NET que se ejecuta en el Servidor de desarrollo de ASP.NET, consulte la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).

> [!NOTE]
> Para crear el servicio de datos de Northwind, instale primero la base de datos de ejemplo Northwind en el equipo local. Para instalar la base de datos, ejecute el script Transact-SQL desde las bases de datos de [ejemplo Northwind y pubs para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).

En este artículo se muestra cómo crear un servicio de datos mediante el proveedor de Entity Framework. Están disponibles otros proveedores de servicios de datos. Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).

Una vez creado el servicio, debe proporcionar acceso a los recursos del servicio de datos de forma explícita. Para obtener más información, consulte [Cómo: habilitar el acceso al servicio de datos](how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Crear la aplicación Web de ASP.NET que se ejecuta en IIS

1. En Visual Studio, en el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

2. En el cuadro de diálogo **nuevo proyecto** , seleccione el > **instalado** [**Visual C#** o **Visual Basic**] > Categoría **Web** .

3. Seleccione la plantilla **Aplicación Web ASP.NET** .

4. Escriba `NorthwindService` como nombre del proyecto.

5. Haga clic en **Aceptar**.

6. En el menú **proyecto** , seleccione **propiedades de NorthwindService**.

7. Seleccione la pestaña **Web** y, a continuación, seleccione **usar servidor Web de IIS local**.

8. Haga clic en **Crear directorio virtual** y, a continuación, en **Aceptar**.

9. Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):

    - Sistemas de 32 bits:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - Sistemas de 64 bits:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     De este modo, se garantiza que Windows Communication Foundation (WCF) se registre en el equipo.

10. Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):

    - Sistemas de 32 bits:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - Sistemas de 64 bits:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Esto garantiza que IIS se ejecuta correctamente una vez instalado WCF en el equipo. Es posible que también tenga que reiniciar IIS.

11. Cuando la aplicación ASP.NET se ejecuta en IIS7, también debe seguir estos pasos:

    1. Abra el administrador de IIS y navegue hasta la aplicación de fotoservicio en **sitio web predeterminado**.

    2. En **Vista Características**, haga doble clic en **Autenticación**.

    3. En la página **Autenticación**, seleccione **Autenticación anónima**.

    4. En el panel **acciones** , haga clic en **Editar** para establecer la entidad de seguridad en la que los usuarios anónimos se conectarán al sitio.

    5. En el cuadro de diálogo **modificar credenciales de autenticación anónima** , seleccione **identidad del grupo de aplicaciones**.

    > [!IMPORTANT]
    > Cuando se usa la cuenta Network Service, se concede a los usuarios anónimos el acceso a toda la red interna asociada a esa cuenta.

12. Desde SQL Server Management Studio, la utilidad sqlcmd.exe o el Editor de Transact-SQL en Visual Studio, ejecute el siguiente comando de Transact-SQL con la instancia de SQL Server que tenga la base de datos Northwind asociada:

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    De este modo, se crea un inicio de sesión en la instancia de SQL Server para la cuenta de Windows utilizada para ejecutar IIS. Esto permite a IIS conectarse a la instancia de SQL Server.

13. Con la base de datos Northwind asociada, ejecute los siguientes comandos de Transact-SQL:

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    Esto otorga derechos al inicio de sesión nuevo, lo que permite a IIS leer y escribir datos en la base de datos Northwind.

## <a name="define-the-data-model"></a>Definir el modelo de datos

1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **ADO.NET Entity Data Model**.

3. Como nombre del modelo de datos, escriba `Northwind.edmx` .

4. En el Asistente para Entity Data Model, seleccione **generar desde la base de datos** y, a continuación, haga clic en **siguiente**.

5. Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:

    - Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y cree una conexión nueva. Para obtener más información, consulta [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.

         \- o -

    - Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.

6. En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.

7. Haga clic en **Finalizar** para cerrar el asistente.

## <a name="create-the-data-service"></a>Crear el servicio de datos

1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **servicio de datos de WCF**.

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.

3. Como nombre del servicio, escriba `Northwind` .

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código. En **Explorador de soluciones**, el servicio tiene el nombre, Northwind, y la extensión. SVC.cs o. SVC. VB.

4. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`. La definición de la clase debería ser como la siguiente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Vea también

- [Exposición de los datos como servicio](exposing-your-data-as-a-service-wcf-data-services.md)
