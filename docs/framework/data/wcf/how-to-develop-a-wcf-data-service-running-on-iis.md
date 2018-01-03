---
title: "Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93b6e8b6e687f2e39fd5792aba08eaa47fa29fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS
Este tema muestra cómo usar [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para crear un servicio de datos que se basa en la base de datos de ejemplo Northwind que está hospedada en una aplicación Web ASP.NET que se ejecuta en Internet Information Services (IIS). Para obtener un ejemplo de cómo crear el mismo servicio de datos de Northwind que una aplicación Web ASP.NET que se ejecuta en el servidor de desarrollo de ASP.NET, vea el [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
> [!NOTE]
>  Para crear el servicio de datos de Northwind, debe tener instalada la base de datos de ejemplo Northwind en el equipo local. Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).  
  
 En este tema se muestra cómo crear un servicio de datos utilizando el proveedor de Entity Framework. Están disponibles otros proveedores de servicios de datos. Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
 Una vez creado el servicio, debe proporcionar acceso a los recursos del servicio de datos de forma explícita. Para obtener más información, consulte [Cómo: habilitar el acceso al servicio de datos](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a>Para crear la aplicación web ASP.NET que se ejecuta en IIS  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **New**y, a continuación, seleccione **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, seleccione Visual Basic o Visual C# como lenguaje de programación.  
  
3.  En el **plantillas** panel, seleccione **aplicación Web ASP.NET**. Nota: si usa Visual Studio Web Developer, tendrá que crear un nuevo sitio web en lugar de una nueva aplicación web.  
  
4.  Tipo `NorthwindService` como el nombre del proyecto.  
  
5.  Haga clic en **Aceptar**.  
  
6.  En el **proyecto** menú, seleccione **propiedades de NorthwindService**.  
  
7.  Seleccione el **Web** pestaña y, a continuación, seleccione **usar servidor Web de IIS Local**.  
  
8.  Haga clic en **crear directorio Virtual** y, a continuación, haga clic en **Aceptar**.  
  
9. Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):  
  
    -   Sistemas de 32 bits:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   Sistemas de 64 bits:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     De este modo, se garantiza que Windows Communication Foundation (WCF) se registre en el equipo.  
  
10. Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):  
  
    -   Sistemas de 32 bits:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   Sistemas de 64 bits:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     Esto garantiza que IIS se ejecuta correctamente una vez instalado WCF en el equipo. Es posible que también tenga que reiniciar IIS.  
  
11. Cuando la aplicación ASP.NET se ejecuta en IIS7, también debe seguir estos pasos:  
  
    1.  Abra el Administrador de IIS y navegue hasta la aplicación PhotoService en **sitio Web predeterminado**.  
  
    2.  En **vista características**, haga doble clic en **autenticación**.  
  
    3.  En el **autenticación** página, seleccione **autenticación anónima**.  
  
    4.  En el **acciones** panel, haga clic en **editar** al establecer la seguridad principal en que los usuarios anónimos se conectarán al sitio.  
  
    5.  En el **modificar credenciales de autenticación anónima** cuadro de diálogo, seleccione **identidad del grupo de aplicaciones**.  
  
    > [!IMPORTANT]
    >  Cuando se usa la cuenta Network Service, se concede a los usuarios anónimos el acceso a toda la red interna asociada a esa cuenta.  
  
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
  
### <a name="to-define-the-data-model"></a>Para definir el modelo de datos  
  
1.  En **el Explorador de soluciones**, haga clic en el nombre del proyecto ASP.NET y, a continuación, haga clic en **Agregar nuevo elemento.**  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **ADO.NET Entity Data Model**.  
  
3.  Para el nombre del modelo de datos, escriba `Northwind.edmx`.  
  
4.  En el Asistente de Entity Data Model, seleccione **generar desde la base de datos**y, a continuación, haga clic en **siguiente**.  
  
5.  Conectar el modelo de datos a la base de datos, realice uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:  
  
    -   Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y crear una nueva conexión. Para obtener más información, consulte [Cómo: crear conexiones a bases de datos de SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631). Esta instancia de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] debe tener adjuntada la base de datos de ejemplo Northwind.  
  
         \- o -  
  
    -   Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.  
  
6.  En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.  
  
7.  Haga clic en **finalizar** para cerrar el asistente.  
  
    > [!NOTE]
    >  Este modelo de datos generado expone las propiedades de clave externa en los tipos de entidad. Los modelos de datos creados mediante Visual Studio 2008 no incluyen estas propiedades de clave externa. Debido a esto, debe actualizar las clases del servicio de datos de cliente de cualquier aplicación cliente que se haya creado para tener acceso al servicio de datos de Northwind que se creó con Visual Studio 2008 antes de intentar tener acceso a esta versión del servicio de datos de Northwind.  
  
### <a name="to-create-the-data-service"></a>Para crear el servicio de datos  
  
1.  En **el Explorador de soluciones**, haga clic en el nombre de su proyecto de ASP.NET y, a continuación, haga clic en **Agregar nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **servicio ADO.NET Data Services**.  
  
3.  Para el nombre del servicio, escriba `Northwind`.  
  
     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código. En **el Explorador de soluciones**, el servicio tendrá el nombre Northwind, con la extensión. svc.cs o. svc.vb.  
  
4.  En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`. La definición de la clase debería ser como la siguiente:  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a>Vea también  
 [Exposición de los datos como servicio](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
