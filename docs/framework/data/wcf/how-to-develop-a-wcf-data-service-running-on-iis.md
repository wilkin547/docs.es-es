---
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
ms.openlocfilehash: 8a1a0c2c55267940463e2c9ab82bb52345269260
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121613"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Cómo: Desarrollar un servicio de datos WCF que se ejecute en IIS

En este artículo se muestra cómo usar Servicios de datos de WCFWCF Data Services para crear un servicio de datos que se basa en la base de datos de ejemplo Northwind hospedada por una aplicación web de ASP.NET que se ejecuta en Internet Information Services (IIS). Para obtener un ejemplo de cómo crear el mismo servicio de datos Northwind como una aplicación web de ASP.NET que se ejecuta en el ASP.NET servidor de desarrollo, vea el inicio rápido de Servicios de [datos de WCF.](quickstart-wcf-data-services.md)

> [!NOTE]
> Para crear el servicio de datos Northwind, instale primero la base de datos de ejemplo Northwind en el equipo local. Para instalar la base de datos, ejecute el script DeTransact-SQL desde [Northwind y las bases](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)de datos de ejemplo pubs para Microsoft SQL Server .

En este artículo se muestra cómo crear un servicio de datos mediante el proveedor de Entity Framework. Están disponibles otros proveedores de servicios de datos. Para obtener más información, vea [Proveedores](data-services-providers-wcf-data-services.md)de servicios de datos .

Una vez creado el servicio, debe proporcionar acceso a los recursos del servicio de datos de forma explícita. Para obtener más información, consulte [Cómo: Habilitar el acceso al servicio](how-to-enable-access-to-the-data-service-wcf-data-services.md)de datos .

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Cree la aplicación web ASP.NET que se ejecuta en IIS

1. En Visual Studio, en el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

2. En el cuadro de diálogo **Nuevo proyecto** , seleccione la categoría **>** [**Visual C** o **Visual Basic**] > **Web.**

3. Seleccione la plantilla **Aplicación Web ASP.NET** .

4. Escriba `NorthwindService` como nombre del proyecto.

5. Haga clic en **OK**.

6. En el menú **Proyecto** , seleccione **Propiedades de NorthwindService**.

7. Seleccione la pestaña **Web** y, a continuación, seleccione Usar servidor **web IIS local**.

8. Haga clic en **Crear directorio virtual** y, a continuación, haga clic en **Aceptar**.

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

    1. Abra el Administrador de IIS y vaya a la aplicación PhotoService en **Sitio Web predeterminado**.

    2. En **Vista Características**, haga doble clic en **Autenticación**.

    3. En la página **Autenticación**, seleccione **Autenticación anónima**.

    4. En el panel **Acciones,** haga clic en **Editar** para establecer la entidad de seguridad en la que los usuarios anónimos se conectarán al sitio.

    5. En el cuadro de diálogo **Editar credenciales de autenticación anónima,** seleccione Identidad del **grupo**de aplicaciones .

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

1. En el **Explorador**de soluciones , haga clic con el botón secundario en el nombre del proyecto ASP.NET y, a continuación, haga clic en **Agregar** > **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione ADO.NET Entity Data **Model**.

3. Para el nombre del modelo `Northwind.edmx`de datos, escriba .

4. En el Asistente para Entity Data Model, seleccione Generar desde **base de datos**y, a continuación, haga clic en **Siguiente**.

5. Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **Siguiente:**

    - Si no tiene una conexión de base de datos ya configurada, haga clic en **Nueva conexión** y cree una nueva conexión. Para obtener más información, consulta [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.

         \- o -

    - Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.

6. En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.

7. Haga clic en **Finalizar** para cerrar el asistente.

## <a name="create-the-data-service"></a>Crear el servicio de datos

1. En el **Explorador**de soluciones , haga clic con el botón secundario en el nombre del proyecto ASP.NET y, a continuación, haga clic en **Agregar** > **nuevo elemento**.

2. En el **agregar nuevo elemento** cuadro de diálogo, seleccione servicio de datos **WCF**.

   ![Plantilla de elemento de servicio de datos wcf en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > La plantilla Servicio de **datos de WCFESTÁ** está disponible en Visual Studio 2015, pero no en Visual Studio 2017 o posterior.

3. Para el nombre del `Northwind`servicio, escriba .

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código. En el Explorador de **soluciones**, el servicio tiene el nombre Northwind y la extensión .svc.cs o .svc.vb.

4. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`. La definición de la clase debería ser como la siguiente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Vea también

- [Exposición de los datos como servicio](exposing-your-data-as-a-service-wcf-data-services.md)
