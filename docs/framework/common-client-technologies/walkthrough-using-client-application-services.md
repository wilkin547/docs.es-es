---
title: 'Tutorial: Usar servicios de aplicaciones cliente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
ms.openlocfilehash: b800848fc3cefb1f82fb5822007bc670c1684363
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43788933"
---
# <a name="walkthrough-using-client-application-services"></a>Tutorial: Usar servicios de aplicaciones cliente
En este tema se describe cómo crear una aplicación de Windows que usa los servicios de aplicaciones cliente para autenticar usuarios y recuperar la configuración y los roles de usuario.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Cree una aplicación de Windows Forms y use el diseñador de proyectos de Visual Studio para habilitar y configurar servicios de aplicaciones cliente.  
  
-   Cree una aplicación simple de servicio web ASP.NET para hospedar los servicios de aplicación y probar la configuración del cliente.  
  
-   Agregue la autenticación mediante formularios a la aplicación. Comenzará usando un nombre de usuario y una contraseña codificados de forma rígida para probar el servicio. A continuación, agregará un formulario de inicio de sesión especificándolo como proveedor de credenciales en la configuración de la aplicación.  
  
-   Agregue funcionalidad basada en roles, habilitando y mostrando un botón solo para los usuarios con el rol de administrador.  
  
-   Acceda a la configuración web. Comenzará cargando la configuración web de un usuario autenticado (de prueba) en la página **Configuración** del diseñador de proyectos. A continuación, usará el Diseñador de Windows Forms para enlazar un cuadro de texto a una configuración web. Por último, guardará el valor modificado en el servidor.  
  
-   Implemente el cierre de sesión. Agregará una opción de cierre de sesión al formulario y llamará a un método de cierre de sesión.  
  
-   Habilite el modo sin conexión. Proporcionará una casilla para que los usuarios puedan especificar su estado de conexión. A continuación, usará este valor para especificar si los proveedores de servicios de aplicaciones cliente usarán los datos almacenados en caché localmente en lugar de acceder a sus servicios web. Por último, volverá a autenticar al usuario actual cuando la aplicación vuelva al modo en línea.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita el componente siguiente para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-client-application"></a>Crear la aplicación cliente.  
 Lo primero que hará es crear un proyecto de Windows Forms. Este tutorial usa Windows Forms porque más personas están familiarizadas con él, pero el proceso es similar para los proyectos de Windows Presentation Foundation (WPF).  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a>Para crear una aplicación cliente y habilitar servicios de aplicaciones cliente  
  
1.  En Visual Studio, seleccione la opción de menú **Archivo &#124; Nuevo &#124; Proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, en el panel **Tipos de proyecto**, expanda el nodo **Visual Basic** o **Visual C#** y seleccione el tipo de proyecto **Windows**.  
  
3.  Asegúrese de que está seleccionado **.NET Framework 3.5** y, a continuación, seleccione la plantilla de **Aplicación de Windows Forms** .  
  
4.  Cambie el valor de **Nombre** del proyecto a `ClientAppServicesDemo`y haga clic en **Aceptar**.  
  
     Se abre un nuevo proyecto de Windows Forms en Visual Studio.  
  
5.  En el menú **Proyecto** , seleccione **Propiedades de ClientAppServicesDemo**.  
  
     Aparece el diseñador de proyectos.  
  
6.  En la pestaña **Servicios** , seleccione **Habilitar servicios de aplicaciones cliente**.  
  
7.  Asegúrese de que esté seleccionada la opción **Usar autenticación de formularios** y, luego, establezca **Ubicación del servicio de autenticación**, **Ubicación del servicio de roles**y **Ubicación del servicio de configuración web** al valor `http://localhost:55555/AppServices`.  
  
8.  En Visual Basic, en la pestaña **Aplicación**, establezca **Modo de autenticación** en **Definido por la aplicación**.  
  
 El diseñador almacena los valores especificados en el archivo app.config de la aplicación.  
  
 En este punto, la aplicación está configurada para acceder a los tres servicios del mismo host. En la siguiente sección, creará el host como una aplicación de servicio web simple, lo que le permite probar la configuración de cliente.  
  
## <a name="creating-the-application-services-host"></a>Crear el host de servicios de aplicación  
 En esta sección, creará una aplicación de servicio web simple que tiene acceso a los datos del usuario desde un archivo de base de datos local de SQL Server Compact. Tras ello, rellenará la base de datos mediante la [ASP.NET Web Site Administration Tool](https://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec). Esta sencilla configuración permite probar rápidamente la aplicación cliente. Como alternativa, puede configurar el host del servicio web para acceder a los datos del usuario desde una base de datos completa de SQL Server o a través de las clases personalizadas <xref:System.Web.Security.MembershipProvider> y <xref:System.Web.Security.RoleProvider> . Para obtener más información, consulta [Creating and Configuring the Application Services Database for SQL Server](https://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2).  
  
 En el siguiente procedimiento, creará y configurará el servicio web AppServices.  
  
#### <a name="to-create-and-configure-the-application-services-host"></a>Para crear y configurar el host de servicios de aplicación  
  
1.  En el **Explorador de soluciones**, seleccione la solución ClientAppServicesDemo y, en el menú **Archivo**, seleccione **Agregar &#124; Nuevo proyecto**.  
  
2.  En el cuadro de diálogo **Agregar nuevo proyecto**, en el panel **Tipos de proyecto**, expanda el nodo **Visual Basic** o **Visual C#** y seleccione el tipo de proyecto **Web**.  
  
3.  Asegúrese de que está seleccionado **.NET Framework 3.5** y, a continuación, seleccione la plantilla de **Aplicación de servicios web ASP.NET** .  
  
4.  Cambie el valor de **Nombre** del proyecto a `AppServices` y haga clic en **Aceptar**.  
  
     Se agrega a la solución un nuevo proyecto de aplicación de servicio web ASP.NET y el archivo Service1.asmx.vb o Service1.asmx.cs aparece en el editor.  
  
    > [!NOTE]
    >  El archivo Service1.asmx.vb o Service1.asmx.cs no se usa en este ejemplo. Si desea mantener el entorno de trabajo despejado, puede cerrarlo y eliminarlo del **Explorador de soluciones**.  
  
5.  En el **Explorador de soluciones**, seleccione el proyecto AppServices y, a continuación, en el menú **Proyecto** , seleccione **Propiedades de AppServices**.  
  
     Aparece el diseñador de proyectos.  
  
6.  En la pestaña **Web** , asegúrese de que está seleccionado **Usar el servidor de desarrollo de Visual Studio** .  
  
7.  Seleccione **Puerto específico**, especifique un valor de `55555`y después establezca el valor de **Ruta de acceso virtual** a `/AppServices`.  
  
8.  Guarde todos los archivos.  
  
9. En el **Explorador de soluciones**, abra el archivo Web.config y busque la etiqueta de apertura `<system.web>` .  
  
10. Agregue el siguiente marcado antes de la etiqueta `<system.web>` .  
  
     Los elementos `authenticationService`, `profileService`y `roleService` de este marcado habilitan y configuran los servicios de aplicación. Para realizar pruebas, el atributo `requireSSL` del elemento `authenticationService` se establece en "false". Los atributos `readAccessProperties` y `writeAccessProperties` del elemento `profileService` indican que la propiedad `WebSettingsTestText` es de lectura/escritura.  
  
    > [!NOTE]
    >  En el código de producción, siempre debería acceder al servicio de autenticación a través de la capa de sockets seguros (SSL, mediante el protocolo HTTPS). Para obtener información sobre cómo configurar SSL, consulte [Configurar la capa de sockets seguros](https://go.microsoft.com/fwlink/?LinkId=91844).  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. Agregue el siguiente marcado después de la etiqueta de apertura `<system.web>` para que esté dentro del elemento `<system.web>` .  
  
     El elemento `profile` configura una sola configuración de sitio web llamada `WebSettingsTestText`.  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 En el siguiente procedimiento, usará la herramienta Administración de sitios web de ASP.NET para completar la configuración del servicio y rellenar el archivo de base de datos local. Agregará dos usuarios, denominados `employee` y `manager` , que pertenecen a dos roles con los mismos nombres. Las contraseñas de usuario son `employee!` y `manager!` , respectivamente.  
  
#### <a name="to-configure-membership-and-roles"></a>Para configurar la pertenencia y los roles  
  
1.  En el **Explorador de soluciones**, seleccione el proyecto AppServices y, a continuación, en el menú **Proyecto** , seleccione **Configuración de ASP.NET**.  
  
     Aparece la **Herramienta Administración de sitios web de ASP.NET** .  
  
2.  En la pestaña **Seguridad** , haga clic en **Usar el Asistente para la configuración de seguridad para configurar la seguridad paso a paso**.  
  
     El **Asistente para configurar la seguridad** aparece y muestra el paso **Página principal** .  
  
3.  Haga clic en **Siguiente**.  
  
     Aparece el paso **Seleccionar el método de acceso** .  
  
4.  Seleccione **Desde Internet**. Esto configura el servicio de modo que use la autenticación mediante formularios en lugar de la autenticación de Windows.  
  
5.  Haga clic en **Siguiente** dos veces.  
  
     Aparece el paso **Definir roles** .  
  
6.  Seleccione **Habilitar los roles para este sitio web**.  
  
7.  Haga clic en **Siguiente**. Aparece el formulario **Crear nuevo rol** .  
  
8.  En el cuadro de texto **Nombre nuevo de rol** , escriba `manager` y, después, haga clic en **Agregar rol**.  
  
     Aparece la tabla **Roles existentes** con el valor especificado.  
  
9. En el cuadro de texto **Nombre nuevo de rol** , reemplace `manager` con `employee` y haga clic en **Agregar rol**.  
  
     El nuevo valor aparece en la tabla **Roles existentes** .  
  
10. Haga clic en **Siguiente**.  
  
     Aparece el paso **Agregar usuarios nuevos** .  
  
11. En el formulario **Crear usuario** , especifique los valores siguientes.  
  
  	|||  
  	|-|-|  
  	|**Nombre de usuario**|`manager`|  
  	|**Contraseña**|`manager!`|  
  	|**Confirmar contraseña**|`manager!`|  
  	|**Correo electrónico**|`manager@contoso.com`|  
  	|**Pregunta de seguridad**|`manager`|  
  	|**Respuesta de seguridad**|`manager`|  
  
12. Haga clic en **Crear usuario**.  
  
     Aparece un mensaje que indica que la operación es correcta.  
  
    > [!NOTE]
    >  En el formulario son necesarios los valores de **Correo electrónico**, **Pregunta de seguridad**y **Respuesta de seguridad**, pero no se usan en este ejemplo.  
  
13. Haga clic en **Continuar**.  
  
     Vuelve a aparecer el formulario **Crear usuario** .  
  
14. En el formulario **Crear usuario** , especifique los valores siguientes.  
  
  	|||  
  	|-|-|  
  	|**Nombre de usuario**|`employee`|  
  	|**Contraseña**|`employee!`|  
  	|**Confirmar contraseña**|`employee!`|  
  	|**Correo electrónico**|`employee@contoso.com`|  
  	|**Pregunta de seguridad**|`Employee`|  
  	|**Respuesta de seguridad**|`employee`|  
  
15. Haga clic en **Crear usuario**.  
  
     Aparece un mensaje que indica que la operación es correcta.  
  
16. Haga clic en **Finalizar**.  
  
     Vuelve a aparecer la **Herramienta Administración de sitios web** .  
  
17. Haga clic en **Usuarios administradores**.  
  
     Aparece la lista de usuarios.  
  
18. Haga clic en **Editar roles** para el usuario **employee** y, a continuación, seleccione el rol **employee** .  
  
19. Haga clic en **Editar roles** para el usuario **manager** y, a continuación, seleccione el rol **manager** .  
  
20. Cierre la ventana del explorador que hospeda la **Herramienta Administración de sitios web**.  
  
21. Si aparece un cuadro de mensaje preguntándole si desea volver a cargar el archivo Web.config modificado, haga clic en **Sí**.  
  
 Esto completa la configuración del servicio web. En este punto, puede presionar F5 para ejecutar la aplicación cliente y el **servidor de desarrollo de ASP.NET** se iniciará automáticamente junto con la aplicación cliente. El servidor seguirá ejecutándose después de que salga de la aplicación, pero se reiniciará cuando reinicie la aplicación. Esto le permite detectar los cambios que haya realizado en Web.config.  
  
 Para detener manualmente el servidor, haga clic con el botón derecho en el icono del servidor de desarrollo de ASP.NET en el área de notificación de la barra de tareas y, a continuación, haga clic en **Detener**. Esto resulta útil en ocasiones para asegurarse de que se produzca un reinicio limpio.  
  
## <a name="adding-forms-authentication"></a>Agregar la autenticación mediante formularios  
 En el siguiente procedimiento, agregará código al formulario principal que intenta validar al usuario y que deniega el acceso cuando el usuario proporciona credenciales no válidas. Usará un nombre de usuario y una contraseña codificados de forma rígida para probar el servicio.  
  
#### <a name="to-validate-the-user-in-your-application-code"></a>Para validar al usuario en el código de aplicación  
  
1.  En el **Explorador de soluciones**, en el proyecto ClientAppServicesDemo, agregue una referencia al ensamblado System.Web.  
  
2.  Seleccione el archivo Form1 y **Vista &#124; Código** en el menú principal de Visual Studio.  
  
3.  En el editor de código, agregue las instrucciones siguientes al principio del archivo Form1.  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]
     [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  En el **Explorador de soluciones**, haga doble clic en Form1 para mostrar el diseñador.  
  
5.  En el diseñador, haga doble clic en la superficie del formulario para generar un controlador de eventos <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> denominado `Form1_Load`.  
  
     Aparece el editor de código con el cursor en el método `Form1_Load` .  
  
6.  Agregue el código siguiente al método `Form1_Load` .  
  
     Este código deniega el acceso a los usuarios no autenticados y sale de la aplicación. Como alternativa, puede permitir que los usuarios no autenticados accedan al formulario, pero denegándoles el acceso a alguna funcionalidad específica. Normalmente, no seguirá este procedimiento para codificar de forma rígida el nombre de usuario y la contraseña, pero resulta útil para realizar pruebas. En la siguiente sección, reemplazará este código por un código más sólido que muestra un cuadro de diálogo de inicio de sesión e incluye control de excepciones.  
  
     Tenga en cuenta que el método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> está en [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]. Este método delega su trabajo en el proveedor de autenticación configurado y devuelve `true` si la autenticación se realiza correctamente. La aplicación no requiere una referencia directa al proveedor de autenticación del cliente.  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]
     [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 Ahora puede presionar F5 para ejecutar la aplicación y, puesto que proporcionó un nombre de usuario y una contraseña correctos, verá el formulario.  
  
> [!NOTE]
>  Si no puede ejecutar la aplicación, intente detener el servidor de desarrollo de ASP.NET. Cuando el servidor se reinicie, compruebe que el puerto está establecido en 55555.  
  
 Si en vez de eso desea ver el mensaje de error, cambie los parámetros <xref:System.Web.Security.Membership.ValidateUser%2A> . Por ejemplo, reemplace el segundo parámetro `"manager!"` con una contraseña incorrecta, como `"MANAGER"`.  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a>Agregar un formulario de inicio de sesión como proveedor de credenciales  
 Puede adquirir las credenciales de usuario en el código de aplicación y pasarlas al método <xref:System.Web.Security.Membership.ValidateUser%2A> . Sin embargo, a menudo resulta útil separar el código de adquisición de credenciales y el código de aplicación, por si desea cambiarlo más adelante.  
  
 En el procedimiento siguiente, configurará la aplicación para que use un proveedor de credenciales y, a continuación, cambiará su llamada al método <xref:System.Web.Security.Membership.ValidateUser%2A> para que pase <xref:System.String.Empty> a ambos parámetros. Las cadenas vacías señalan el método <xref:System.Web.Security.Membership.ValidateUser%2A> para llamar al método <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> del proveedor de credenciales configurado.  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a>Para configurar la aplicación de modo que use un proveedor de credenciales  
  
1.  En el **Explorador de soluciones**, seleccione el proyecto ClientAppServicesDemo y, a continuación, en el menú **Proyecto** , seleccione **Propiedades de ClientAppServicesDemo**.  
  
     Aparece el diseñador de proyectos.  
  
2.  En la pestaña **Servicios** , establezca **Opcional: proveedor de credenciales** en el valor siguiente. Este valor indica el nombre de tipo calificado con el ensamblado.  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  En el archivo de código Form1, reemplace el código del método `Form1_Load` por el siguiente código.  
  
     Este código muestra un mensaje de bienvenida y, a continuación, llama al método `ValidateUsingCredentialsProvider` que agregará en el paso siguiente. Si el usuario no está autenticado, el método `ValidateUsingCredentialsProvider` devuelve `false` y se devuelve el método `Form1_Load` . Esto impide la ejecución de código adicional antes de salir de la aplicación. El mensaje de bienvenida es útil para indicar cuándo se reinicia la aplicación. Agregará código para reiniciar la aplicación al implementar el cierre de sesión más adelante en este tutorial.  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]
     [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  Agregue el método siguiente después del método `Form1_Load` .  
  
     Este método pasa cadenas vacías al método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> , que hace que aparezca el cuadro de diálogo de inicio de sesión. Si el servicio de autenticación no está disponible, el método <xref:System.Web.Security.Membership.ValidateUser%2A> producirá una <xref:System.Net.WebException>. En este caso, el método `ValidateUsingCredentialsProvider` muestra un mensaje de advertencia y pregunta al usuario si desea volver a intentarlo en modo sin conexión. Esta funcionalidad requiere la característica **Guardar hash de contraseña para permitir el inicio de sesión sin conexión** que se describe en [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). Esta característica está habilitada de manera predeterminada para los proyectos nuevos.  
  
     Si no se valida el usuario, el método `ValidateUsingCredentialsProvider` muestra un mensaje de error y sale de la aplicación. Por último, este método devuelve el resultado del intento de autenticación.  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]
     [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a>Crear un formulario de inicio de sesión  
 Un proveedor de credenciales es una clase que implementa la interfaz <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> . Esta interfaz tiene un método único denominado <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> que devuelve un objeto <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> . Los procedimientos siguientes describen cómo crear un cuadro de diálogo de inicio de sesión que implementa <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> para que aparezca y devuelva las credenciales especificadas por el usuario.  
  
 Se proporcionan procedimientos independientes para Visual Basic y C# porque Visual Basic proporciona una plantilla **Formulario de inicio de sesión**. Esto ahorra tiempo y esfuerzo de codificación.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a>Para crear un cuadro de diálogo de inicio de sesión como proveedor de credenciales en Visual Basic  
  
1.  En el **Explorador de soluciones**, seleccione el proyecto ClientAppServicesDemo y, a continuación, en el menú **Proyecto** , seleccione **Agregar nuevo elemento**.  
  
2.  En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **Formulario de inicio de sesión** , cambie el valor de **Nombre** del elemento a `Login.vb`y haga clic en **Agregar**.  
  
     El cuadro de diálogo de inicio de sesión aparece en el Diseñador de Windows Forms.  
  
3.  En el diseñador, seleccione el botón **Aceptar** y, a continuación, en la ventana **Propiedades** , establezca `DialogResult` en `OK`.  
  
4.  En el diseñador, agregue un control `CheckBox` al formulario en el cuadro de texto **Contraseña** .  
  
5.  En la ventana **Propiedades**, especifique un valor **(Nombre)** de `rememberMeCheckBox` y un valor **Texto** de `&Remember me`.  
  
6.  Seleccione **Vista &#124; Código** en el menú principal de Visual Studio.  
  
7.  En el Editor de código, agregue el siguiente código al principio del archivo.  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  Modifique la firma de la clase de modo que la clase implemente la interfaz <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> .  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. Asegúrese de que el cursor está después de `IClientformsAuthenticationCredentialsProvider`y, a continuación, presione ENTRAR para generar el método `GetCredentials` .  
  
10. Busque la implementación de <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> y, a continuación, reemplácela por el código siguiente.  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 El siguiente procedimiento de C# proporciona toda la lista de código de un cuadro de diálogo de inicio de sesión simple. El diseño de este cuadro de diálogo es un poco tosco, pero lo importante es la implementación de <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> .  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a>Para crear un cuadro de diálogo de inicio de sesión como proveedor de credenciales en C#  
  
1.  En el **Explorador de soluciones**, seleccione el proyecto ClientAppServicesDemo y, a continuación, en el menú **Proyecto** , seleccione **Agregar clase**.  
  
2.  En el cuadro de diálogo **Agregar nuevo elemento** , cambie el valor de **Nombre** a `Login.cs`y haga clic en **Agregar**.  
  
     Se abre el archivo Login.cs en el editor de código.  
  
3.  Reemplace el código predeterminado por el siguiente código.  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 Ahora puede ejecutar la aplicación, y verá que aparece el cuadro de diálogo de inicio de sesión. Para probar este código, ensaye con credenciales diferentes, tanto válidas como no válidas, y confirme que solo puede acceder al formulario con credenciales válidas. Los nombres de usuario válidos son `employee` y `manager` , con las contraseñas `employee!` y `manager!` , respectivamente.  
  
> [!NOTE]
>  No seleccione **Recordar mi cuenta** en este punto o no podrá iniciar sesión como otro usuario hasta que implemente el cierre de sesión más adelante en este tutorial.  
  
## <a name="adding-role-based-functionality"></a>Agregar funcionalidad basada en roles  
 En el siguiente procedimiento, agregará un botón al formulario y lo mostrará únicamente a los usuarios con el rol de administrador.  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a>Para cambiar la interfaz de usuario en función del rol de usuario  
  
1.  En el **Explorador de soluciones**, en el proyecto ClientAppServicesDemo, seleccione Form1 y **Vista &#124; Diseñador** en el menú principal de Visual Studio.  
  
2.  En el diseñador, agregue un control <xref:System.Windows.Forms.Button> al formulario desde el **Cuadro de herramientas**.  
  
3.  En la ventana **Propiedades** , establezca las propiedades siguientes del botón.  
  
  	|Propiedad.|Valor|  
  	|--------------|-----------|  
  	|**(Nombre)**|managerOnlyButton|  
  	|**Texto**|&Manager task|  
  	|**Visible**|`False`|  
  
4.  En el editor de código para el Form1, agregue el siguiente código al final del método `Form1_Load` .  
  
     Este código llama al método `DisplayButtonForManagerRole` que agregará en el paso siguiente.  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]
     [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  Agregue el siguiente método al final de la clase Form1.  
  
     Este método llama al método <xref:System.Security.Principal.IPrincipal.IsInRole%2A> del objeto <xref:System.Security.Principal.IPrincipal> devuelto por la propiedad `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> . Para las aplicaciones configuradas para usar servicios de aplicaciones cliente, esta propiedad devuelve <xref:System.Web.ClientServices.ClientRolePrincipal>. Dado que esta clase implementa la interfaz <xref:System.Security.Principal.IPrincipal> , no es necesario hacer referencia a esta explícitamente.  
  
     Si el usuario tiene el rol de administrador, el método `DisplayButtonForManagerRole` establece la propiedad <xref:System.Windows.Forms.Control.Visible%2A> de `managerOnlyButton` en `true`. Este método también muestra un mensaje de error si se produce una <xref:System.Net.WebException> , lo que indica que el servicio de roles no está disponible.  
  
    > [!NOTE]
    >  El método <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> siempre devolverá `false` si el inicio de sesión de usuario expiró. Esto no sucederá si la aplicación llama al método <xref:System.Security.Principal.IPrincipal.IsInRole%2A> poco después de la autenticación, como se muestra en el código de ejemplo de este tutorial. Si la aplicación debe recuperar los roles de usuario en otras ocasiones, conviene agregar código para volver a validar a los usuarios cuyo inicio de sesión haya expirado. Si todos los usuarios válidos están asignados a roles, puede determinar si el inicio de sesión expiró llamando al método <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> . Si no se devuelve ningún rol, el inicio de sesión expiró. Para obtener un ejemplo de esta funcionalidad, consulte el método <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> . Esta funcionalidad solo es necesaria si seleccionó **Exigir que los usuarios vuelvan a iniciar sesión cuando expire la cookie del servidor** en la configuración de la aplicación. Para obtener más información, consulte [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]
     [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 Si la autenticación es correcta, el proveedor de autenticación del cliente establece la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> en una instancia de la clase <xref:System.Web.ClientServices.ClientRolePrincipal>. Esta clase implementa el método <xref:System.Security.Principal.IPrincipal.IsInRole%2A> para que el trabajo se delegue en el proveedor de roles configurado. Al igual que antes, el código de aplicación no requiere una referencia directa al proveedor de servicios.  
  
 Ahora puede ejecutar la aplicación e iniciar sesión como empleado para comprobar que el botón no aparece y, a continuación, iniciar sesión como administrador para ver el botón.  
  
## <a name="accessing-web-settings"></a>Acceder a la configuración web  
 En el siguiente procedimiento, agregará un cuadro de texto al formulario y lo enlazará a una configuración web. Al igual que el código anterior, que usa autenticación y roles, el código de configuración no accede al proveedor de configuración directamente. En su lugar, usa la clase `Settings` fuertemente tipada (a la que se accede como `Properties.Settings.Default` en C# y como `My.Settings` en Visual Basic) que Visual Studio genera para el proyecto.  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a>Para usar la configuración web en la interfaz de usuario  
  
1.  Compruebe el área de notificación de la barra de tareas para asegurarse de que el **servidor de desarrollo web de ASP.NET** sigue ejecutándose. Si el servidor se detuvo, reinicie la aplicación (que inicia automáticamente el servidor) y cierre el cuadro de diálogo de inicio de sesión.  
  
2.  En el **Explorador de soluciones**, seleccione el proyecto ClientAppServicesDemo y, a continuación, en el menú **Proyecto** , seleccione **Propiedades de ClientAppServicesDemo**.  
  
     Aparece el diseñador de proyectos.  
  
3.  En la pestaña **Configuración** , haga clic en **Cargar configuración web**.  
  
     Aparece el cuadro de diálogo **Inicio de sesión** .  
  
4.  Escriba las credenciales del empleado o del administrador y haga clic en **Inicio de sesión**. La configuración web que usará está configurada para permitir el acceso únicamente a los usuarios autenticados, por lo que si hace clic en **Omitir inicio de sesión** no se cargará ningún ajuste de configuración.  
  
     El ajuste de configuración `WebSettingsTestText` aparece en el diseñador con el valor predeterminado de `DefaultText`. Además, se genera para el proyecto una clase `Settings` que contiene una propiedad `WebSettingsTestText`.  
  
5.  En el **Explorador de soluciones**, en el proyecto ClientAppServicesDemo, seleccione Form1 y **Vista &#124; Diseñador** en el menú principal de Visual Studio.  
  
6.  En el diseñador, agregue un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
7.  En la ventana **Propiedades** , especifique **como valor de** (Nombre) `webSettingsTestTextBox`.  
  
8.  En el editor de código, agregue el siguiente código al final del método `Form1_Load` .  
  
     Este código llama al método `BindWebSettingsTestTextBox` que agregará en el paso siguiente.  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]
     [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. Agregue el siguiente método al final de la clase Form1.  
  
     Este método enlaza la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> de `webSettingsTestTextBox` con la propiedad `WebSettingsTestText` de la clase `Settings` generada anteriormente en este procedimiento. Este método también muestra un mensaje de error si se produce una <xref:System.Net.WebException> , lo que indica que el servicio de configuración web no está disponible.  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]
     [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  Normalmente, usará el enlace de datos para habilitar la comunicación bidireccional automática entre un control y una configuración web. Sin embargo, también puede acceder a la configuración web directamente, tal como se muestra en el ejemplo siguiente:  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]
     [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. En el diseñador, seleccione el formulario y, en la ventana **Propiedades** , haga clic en el botón **Eventos** .  
  
11. Seleccione el evento <xref:System.Windows.Forms.Form.FormClosing> y, a continuación, presione ENTRAR para generar un controlador de eventos.  
  
12. Reemplace el método generado con el código siguiente.  
  
     El controlador de eventos <xref:System.Windows.Forms.Form.FormClosing> llama al método `SaveSettings` , que la funcionalidad de cierre de sesión que agregará en la sección siguiente también usa. El método `SaveSettings` confirma primero que el usuario no cerró sesión. Esto lo hace comprobando la propiedad <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> del objeto <xref:System.Security.Principal.IIdentity> devuelto por la entidad de seguridad actual. La entidad de seguridad actual se recupera mediante la propiedad `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> . Si el usuario se autenticó para los servicios de aplicaciones cliente, el tipo de autenticación será "ClientForms". El método `SaveSettings` no puede comprobar la propiedad <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> porque el usuario podría tener una identidad de Windows válida después de cerrar la sesión.  
  
     Si el usuario no cerró la sesión, el método `SaveSettings` llama al método <xref:System.Configuration.ApplicationSettingsBase.Save%2A> de la clase `Settings` generada anteriormente en este procedimiento. Este método puede producir una <xref:System.Net.WebException> si la cookie de autenticación expiró. Esto sucede únicamente si seleccionó **Exigir que los usuarios vuelvan a iniciar sesión cuando expire la cookie del servidor** en la configuración de la aplicación. Para obtener más información, consulte [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). El método `SaveSettings` controla la expiración de la cookie llamando a <xref:System.Web.Security.Membership.ValidateUser%2A> para mostrar el cuadro de diálogo de inicio de sesión. Si el usuario inicia sesión correctamente, el método `SaveSettings` intenta guardar la configuración de nuevo llamándose a sí mismo.  
  
     Al igual que en el código anterior, el método `SaveSettings` muestra un mensaje de error si el servicio remoto no está disponible. Si el proveedor de configuración no puede acceder al servicio remoto, la configuración sigue guardándose en la memoria caché local y se vuelve a cargar cuando se reinicia la aplicación.  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]
     [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. Agregue el siguiente método al final de la clase Form1.  
  
     Este código controla el evento <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> y muestra una advertencia si no se pudo guardar alguno de los valores de configuración. El evento <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> no se produce si el servicio de configuración no está disponible o si la cookie de autenticación expiró. El evento <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> se producirá, por ejemplo, cuando el usuario ya haya cerrado la sesión. Puede probar este controlador de eventos agregando código de cierre de sesión al método `SaveSettings` directamente antes de la llamada al método <xref:System.Configuration.ApplicationSettingsBase.Save%2A> . El código de cierre de sesión que puede usar se describe en la sección siguiente.  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]
     [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. En el caso de C#, agregue el código siguiente al final del método `Form1_Load` . Este código asocia el método que agregó en el último paso con el evento <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> .  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 Para probar la aplicación en este punto, ejecútela varias veces como empleado y como administrador, y especifique valores diferentes en el cuadro de texto. Los valores se conservarán en las sesiones de cada usuario.  
  
## <a name="implementing-logout"></a>Implementar el cierre de sesión  
 Cuando el usuario selecciona la casilla **Recordar mi cuenta** al iniciar sesión, la la aplicación autenticará automáticamente al usuario en las ejecuciones posteriores. La autenticación automática seguirá produciéndose mientras la aplicación esté en modo sin conexión o hasta que expire la cookie de autenticación. Sin embargo, en ocasiones, varios usuarios necesitarán acceder a la aplicación, o un usuario podría iniciar sesión con credenciales diferentes. Para habilitar este escenario, debe implementar la funcionalidad de cierre de sesión, tal como se describe en el procedimiento siguiente.  
  
#### <a name="to-implement-logout-functionality"></a>Para implementar la funcionalidad de cierre de sesión  
  
1.  En el diseñador de Form1, agregue un control <xref:System.Windows.Forms.Button> al formulario desde el **Cuadro de herramientas**.  
  
2.  En la ventana **Propiedades**, especifique `logoutButton` como valor de **(Nombre)** y **&Cerrar sesión** como valor de **Texto**.  
  
3.  Haga doble clic en `logoutButton` para generar un controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
     Aparece el editor de código con el cursor en el método `logoutButton_Click` .  
  
4.  Reemplace el método `logoutButton_Click` generado con el código siguiente.  
  
     Este controlador de eventos llama primero al método `SaveSettings` que agregó en la sección anterior. A continuación, el controlador de eventos llama al método <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> . Si el servicio de autenticación no está disponible, el método <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> producirá una <xref:System.Net.WebException>. En este caso, el método `logoutButton_Click` muestra un mensaje de advertencia y pasa temporalmente al modo sin conexión para cerrar la sesión del usuario. El modo sin conexión se describe en la sección siguiente.  
  
     El cierre de sesión elimina la cookie de autenticación local para que vuelva a solicitarse el inicio de sesión cuando se reinicie la aplicación. Después de cerrar la sesión, el controlador de eventos reinicia la aplicación. Cuando se reinicia la aplicación, muestra el mensaje de bienvenida seguido del cuadro de diálogo de inicio de sesión. El mensaje de bienvenida deja claro que se reinició la aplicación. Esto evita una posible confusión si el usuario debe iniciar sesión para guardar la configuración y, a continuación, debe volver a iniciar sesión porque la aplicación se reinició.  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]
     [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 Para probar la funcionalidad de cierre de sesión, ejecute la aplicación y seleccione **Recordar mi cuenta** en el cuadro de diálogo de inicio de sesión. A continuación, cierre y reinicie la aplicación para confirmar que ya no debe iniciar sesión. Por último, reinicie la aplicación haciendo clic en Cerrar sesión.  
  
## <a name="enabling-offline-mode"></a>Habilitar el modo sin conexión  
 En el siguiente procedimiento, agregará una casilla al formulario para que el usuario pueda entrar en modo sin conexión. La aplicación indica el modo sin conexión estableciendo la propiedad `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> en `true`. El estado sin conexión se almacena en el disco duro local en la ubicación indicada por la propiedad <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> . Esto significa que el estado sin conexión se almacena por usuario y aplicación.  
  
 En el modo sin conexión, todas las solicitudes de servicio de aplicaciones cliente recuperan datos de la memoria caché local, en lugar de intentar acceder a los servicios. En la configuración predeterminada, los datos locales incluyen un formulario cifrado con la contraseña del usuario. Esto permite al usuario iniciar sesión mientras la aplicación está en modo sin conexión. Para obtener más información, consulta [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
#### <a name="to-enable-offline-mode-in-your-application"></a>Para habilitar el modo sin conexión en la aplicación  
  
1.  En el **Explorador de soluciones**, en el proyecto ClientAppServicesDemo, seleccione Form1 y **Vista &#124; Diseñador** en el menú principal de Visual Studio.  
  
2.  En el diseñador, agregue un control <xref:System.Windows.Forms.CheckBox> al formulario.  
  
3.  En la ventana **Propiedades**, especifique `workOfflineCheckBox` como valor de **(Nombre)** y **&Trabajar sin conexión** como valor de **Texto**.  
  
4.  En la ventana **Propiedades** , haga clic en el botón **Eventos** .  
  
5.  Seleccione el evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> y, a continuación, presione ENTRAR para generar un controlador de eventos.  
  
6.  Reemplace el método generado con el código siguiente.  
  
     Este código actualiza el valor <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> y vuelve a validar al usuario de forma automática cuando regresa al modo en línea. El método <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> usa las credenciales almacenadas en caché para que el usuario no tenga que iniciar sesión explícitamente. Si el servicio de autenticación no está disponible, aparece un mensaje de advertencia y la aplicación se queda sin conexión.  
  
    > [!NOTE]
    >  El método <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> es solo para su comodidad. Dado que no tiene un valor devuelto, no puede indicar si hubo un error de validación. La revalidación puede producir un error, por ejemplo, si las credenciales del usuario cambiaron en el servidor. En este caso, quizás desee incluir código que valida explícitamente a los usuarios después de que se produzca un error en una llamada al servicio. Para obtener más información, vea la sección Acceder a la configuración web anteriormente en este tutorial.  
  
     Después de la revalidación, este código guarda cualquier cambio en la configuración web local llamando al método `SaveSettings` que agregó anteriormente. Luego recupera los valores nuevos del servidor al llamar al método <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> de la clase `Settings` del proyecto (a la que se accede como `Properties.Settings.Default` en C# y como `My.Settings` en Visual Basic).  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]
     [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  Agregue el código siguiente al final del método `Form1_Load` para asegurarse de que la casilla muestra el estado de conexión actual.  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]
     [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 Con esto finaliza la aplicación del ejemplo. Para probar la funcionalidad sin conexión, ejecute la aplicación, inicie sesión como empleado o como administrador y seleccione **Trabajar sin conexión**. Modifique el valor del cuadro de texto y, a continuación, cierre la aplicación. Reinicie la aplicación. Antes de iniciar sesión, haga clic con el botón derecho en el icono del servidor de desarrollo de ASP.NET en el área de notificación de la barra de tareas y, después, haga clic en **Detener**. A continuación, inicie sesión como lo haría normalmente. Incluso si no se está ejecutando el servidor, podrá iniciar sesión. Modifique el valor del cuadro de texto, salga y reinicie para ver el valor modificado.  
  
## <a name="summary"></a>Resumen  
 En este tutorial, aprendió a habilitar y usar servicios de aplicaciones cliente en una aplicación de Windows Forms. Después de configurar un servidor de prueba, agregó código a la aplicación para autenticar a los usuarios y recuperar los roles de usuario y la configuración de la aplicación del servidor. También aprendió a habilitar el modo sin conexión para que la aplicación use una caché de datos local en lugar de los servicios remotos cuando la conectividad no está disponible.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En una aplicación real, accederá a datos de muchos usuarios desde un servidor remoto que podría no estar siempre disponible, o que podría fallar sin previo aviso. Para que la aplicación sea sólida, debe responder apropiadamente a situaciones en las que el servicio no esté disponible. Este tutorial incluye bloques try/catch para detectar una <xref:System.Net.WebException> y mostrar un mensaje de error cuando el servicio no está disponible. En el código de producción, quizás desee controlar este caso cambiando al modo sin conexión, saliendo de la aplicación o denegando el acceso a una funcionalidad específica.  
  
 Para aumentar la seguridad de su aplicación, asegúrese de probar exhaustivamente la aplicación y el servidor antes de la implementación.  
  
## <a name="see-also"></a>Vea también  
 [Servicios de aplicación cliente](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Información general sobre los servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Herramienta de administración de sitios web de ASP.NET](https://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)  
 [Crear y configurar la base de datos de servicios de la aplicación para SQL Server](https://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)  
 [Tutorial: Usar servicios de aplicación ASP.NET](https://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)
