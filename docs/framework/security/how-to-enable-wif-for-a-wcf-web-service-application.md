---
title: "C&#243;mo habilitar WIF para una aplicaci&#243;n de servicio web WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# C&#243;mo habilitar WIF para una aplicaci&#243;n de servicio web WCF
## Se aplica a  
  
-   Microsoft® Windows® Identity Foundation \(WIF\)  
  
-   Microsoft® Windows® Communication Foundation \(WCF\)  
  
## Resumen  
 En este tema de procedimientos se proporcionan los procedimientos paso a paso detallados para habilitar WIF en un servicio Web de WCF.  También se proporcionan instrucciones sobre cómo probar la aplicación para comprobar que el servicio Web está presentando notificaciones correctamente cuando se ejecuta la aplicación.  Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad \(STS\) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool.  El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas.  Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool.  Se puede descargar en la siguiente ubicación: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 – Crear un servicio WCF simple  
  
-   Paso 2 – Crear una aplicación cliente para el servicio WCF  
  
-   Paso 3 – Probar la solución  
  
## Objetivos  
  
-   Crear un servicio WCF que requiera tokens emitidos  
  
-   Crear un cliente WCF que solicite un token de un STS y lo pase al servicio WCF  
  
## Información general  
 El objetivo de este tema de procedimientos es demostrar la manera en que un desarrollador puede utilizar la autenticación federada cuando desarrolle servicios WCF.  Entre las ventajas del uso de la federación en servicios WCF se incluyen las siguientes:  
  
1.  La factorización de la lógica de autenticación fuera del código de servicio WCF  
  
2.  La reutilización de las soluciones de administración de identidades existentes  
  
3.  Interoperabilidad con otras soluciones de identidad  
  
4.  Flexibilidad y resistencia a cambios futuros  
  
 WIF con la extensión Identity and Access Tool asociada facilitan el desarrollo y las pruebas de un servicio WCF mediante autenticación federada, como muestran los pasos siguientes.  
  
## Resumen de pasos  
  
-   Paso 1 – Crear un servicio WCF simple  
  
-   Paso 2 – Crear una aplicación cliente para el servicio WCF  
  
-   Paso 3 – Probar la solución  
  
## Paso 1 – Crear un servicio WCF simple  
 En este paso, creará un nuevo servicio WCF que utilice el STS de desarrollo que se incluye con la herramienta Identity and Access Tool.  
  
#### Para crear un servicio WCF simple  
  
1.  Inicie Visual Studio como administrador con permisos elevados.  
  
2.  En Visual Studio, haga clic en **Archivo**, en **Nuevo** y, a continuación, en **Proyecto**.  
  
3.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación de servicios WCF**.  
  
4.  En **Nombre**, escriba `TestService` y presione **Aceptar**.  
  
5.  Haga clic con el botón secundario en el proyecto **TestService** en el **Explorador de soluciones** y seleccione **Identity and Access**.  
  
6.  Aparecerá la ventana **Identity and Access**.  En **Providers**, seleccione **Test your application with the Local Development STS** y haga clic en **Aplicar**.  Identity and Access Tool configura el servicio para usar WIF y externalizar la autenticación al STS de desarrollo local \(**LocalSTS**\) agregando elementos de configuración al archivo *web.config*.  
  
7.  En el archivo *Service1.svc.cs*, agregue una directiva `using` para el espacio de nombres **System.Security.Claims** y reemplace el código existente por el siguiente; a continuación, guarde el archivo:  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     El método `ComputeResponse` muestra las propiedades de las distintas notificaciones emitidas por **LocalSTS**.  
  
8.  En el archivo *IService1.cs*, reemplace el código existente por el siguiente y, a continuación, guarde el archivo:  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. Compile el proyecto.  
  
10. Presione **Ctrl\-F5** para ejecutar el servicio sin iniciar el depurador.  Se debería abrir una página web para el servicio y podrá comprobar que **LocalSTS** se está ejecutando examinando el área de notificaciones \(la bandeja del sistema\).  
  
    > [!IMPORTANT]
    >  **TestService** y **LocalSTS** deben estar en ejecución cuando se agrega una referencia de servicio a la aplicación cliente en el paso siguiente.  
  
## Paso 2 – Crear una aplicación cliente para el servicio WCF  
 En este paso creará una aplicación de consola que utiliza el STS de desarrollo para autenticarse con el servicio WCF que creó en el paso anterior.  
  
#### Para crear una aplicación cliente  
  
1.  En Visual Studio, haga clic con el botón secundario en la solución, haga clic en **Agregar** y, a continuación, en **Nuevo proyecto**.  
  
2.  En la ventana **Agregar nuevo proyecto**, seleccione **Aplicación de consola** en la lista de plantillas de **Visual C\#**, escriba `Client` y presione **Aceptar**.  El nuevo proyecto se creará en la carpeta de la solución.  
  
3.  Haga clic con el botón secundario en **Referencias** debajo del proyecto **Cliente** y, a continuación, haga clic en **Agregar referencia de servicio**.  
  
4.  En la ventana **Agregar referencia de servicio**, haga clic en la flecha desplegable del botón **Detectar** y en **Servicios de la solución**.  La **Dirección** se rellenará automáticamente con el servicio WCF que creó anteriormente y el **Espacio de nombres** se establecerá en **ServiceReference1**.  Haga clic en **Aceptar**.  
  
    > [!IMPORTANT]
    >  **TestService** y **LocalSTS** deben estar en ejecución cuando se agregue la referencia de servicio al cliente.  
  
5.  Visual Studio generará clases de proxy para el servicio WCF y agregará toda la información de referencia necesaria.  También agregará elementos al archivo *App.config* para configurar el cliente para que obtenga un token del STS a fin de autenticarse con el servicio.  Cuando este proceso haya acabado, se abrirá el archivo **Program.cs**.  Agregue una directiva `using` para **System.ServiceModel** y otra para **Client.ServiceReference1**, reemplace el método **Principal** con el código siguiente y, a continuación, guarde el archivo:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  Abra el archivo *app.config* y agregue el siguiente código XML como el primer elemento secundario bajo el elemento `<system.serviceModel>`; después, guarde el archivo:  
  
    ```  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
  
    ```  
  
     Esto deshabilita la validación de certificados.  
  
7.  Haga clic con el botón secundario en la solución **TestService** y haga clic en **Establecer proyectos de inicio**.  Se abre la página de propiedades **Proyecto de inicio**.  En la página de propiedades **Proyecto de inicio**, seleccione **Varios proyectos de inicio** y, a continuación, haga clic en el campo **Acción** para cada proyecto y seleccione **Iniciar** en el menú desplegable.  Haga clic en **Aceptar** para guardar la configuración.  
  
8.  Compile la solución.  
  
## Paso 3 – Probar la solución  
 En este paso probará la aplicación WCF habilitada para WIF y comprobará que se presentan las notificaciones.  
  
#### Para probar la aplicación WCF habilitada para WIF para las notificaciones  
  
1.  Presione **F5** para compilar y ejecutar la aplicación.  Debe aparecer una ventana de la consola y el texto siguiente: **Press Enter key to invoke service, any other key to quit application:**  
  
2.  Presione **Entrar**; en la consola debería aparecer la siguiente información de las notificaciones:  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  **TestService** y **LocalSTS** deben estar en ejecución antes de presionar **Entrar**.  Se debería abrir una página web para el servicio y podrá comprobar que **LocalSTS** se está ejecutando examinando el área de notificaciones \(la bandeja del sistema\).  
  
3.  Si estas notificaciones aparecen en la consola, ha autenticado correctamente con el STS para mostrar notificaciones desde el servicio WCF.