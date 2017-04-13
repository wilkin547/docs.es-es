---
title: "C&#243;mo mostrar el estado “Firmado” mediante WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# C&#243;mo mostrar el estado “Firmado” mediante WIF
## Se aplica a  
  
-   Microsoft® Windows® Identity Foundation \(WIF\) 4.5  
  
-   Formularios Web Forms ASP.NET®  
  
## Resumen  
 En este tema se describe cómo mostrar el estado de inicio de sesión en una aplicación ASP.NET habilitada para WIF.  WIF proporciona el mecanismo para que la aplicación reconozca las notificaciones y administre la autenticación y la autorización de los recursos de la aplicación.  
  
## Contenido  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 \- Instalar la extensión Identity and Access  
  
-   Paso 2 \- Crear una aplicación ASP.NET de usuario de confianza  
  
-   Paso 3 \- Habilitar STS de desarrollo local para autenticar usuarios  
  
-   Paso 4 \- Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión  
  
-   Paso 5 \- Probar la integración entre WIF y la aplicación ASP.NET  
  
## Información general  
 En este tema se muestra cómo crear una aplicación sencilla que reconozca notificaciones mediante WIF y la manera de determinar con facilidad si un usuario ha iniciado sesión o no.  Los pasos siguientes utilizan el STS de desarrollo local que se incluye con la extensión de Visual Studio Identity and Access.  El STS de desarrollo local está pensado para que un entorno de desarrollo y pruebas proporcione un método sencillo para integrar notificaciones en la aplicación.  Nunca se debe usar en un entorno de producción, ya que no realiza la autenticación real y no se requieren credenciales.  Sin embargo, el código imperativo de los pasos siguientes es el mismo para una aplicación lista para producción que usa autenticación real.  
  
## Resumen de pasos  
  
-   Paso 1 \- Instalar la extensión Identity and Access  
  
-   Paso 2 \- Crear una aplicación ASP.NET de usuario de confianza  
  
-   Paso 3 \- Habilitar STS de desarrollo local para autenticar usuarios  
  
-   Paso 4 \- Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión  
  
-   Paso 5 \- Probar la integración entre WIF y la aplicación ASP.NET  
  
## Paso 1 \- Instalar la extensión Identity and Access  
 Este paso describe la manera de configurar la extensión Identity and Access en Visual Studio 2012.  Esta extensión automatiza el proceso de configuración de la aplicación para comunicarse con los extremos de STS.  
  
#### Para instalar la extensión Identity and Access  
  
1.  Inicie Visual Studio como administrador con permisos elevados.  
  
2.  En Visual Studio, haga clic en **Herramientas** y en **Administrador de extensiones**.  Aparece la ventana **Administrador de extensiones**.  
  
3.  En el **Administrador de extensiones**, haga clic en **Extensiones en línea** en el menú izquierdo y, a continuación, seleccione **Galería de Visual Studio**.  
  
4.  En la esquina superior derecha del **Administrador de extensiones**, busque *Identity and Access*.  
  
5.  El elemento **Identity and Access** aparecerá en los resultados de la búsqueda.  Haga clic en él y, a continuación, en **Descargar**.  
  
6.  Aparece el cuadro de diálogo **Descargar e instalar**.  Si está de acuerdo con los términos de la licencia, haga clic en **Instalar**.  
  
7.  Cuando la extensión **Identity and Access** haya acabado de instalarse, reinicie Visual Studio en modo de administrador.  
  
## Paso 2 \- Crear una aplicación ASP.NET de usuario de confianza  
 Este paso describe la manera de crear una aplicación de formularios Web Forms ASP.NET de usuario de confianza que se integrará con WIF.  
  
#### Para crear una aplicación de ASP.NET sencilla  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y en **Proyecto**.  
  
2.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
3.  En **Nombre**, escriba `TestApp` y presione **Aceptar**.  
  
## Paso 3 \- Habilitar STS de desarrollo local para autenticar usuarios  
 Este paso describe cómo habilitar el STS de desarrollo local en la aplicación.  El STS de desarrollo local se habilita utilizando la extensión Identity and Access de Visual Studio.  
  
#### Para habilitar el STS de desarrollo local en la aplicación ASP.NET  
  
1.  En Visual Studio, haga clic con el botón secundario en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.  
  
2.  Aparecerá la ventana **Identity and Access**.  En **Providers**, seleccione **Test your application with the Local Development STS** y haga clic en **Aplicar**.  
  
## Paso 4 \- Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión  
 Este paso describe la manera de modificar la aplicación ASP.NET para que muestre de manera dinámica si el usuario actual ha iniciado sesión.  Una vez configurado el proveedor de STS, WIF controla las notificaciones de entrada.  Ahora debe configurar el código de la aplicación para mostrar el resultado de la autenticación.  
  
#### Para mostrar el estado de inicio de sesión  
  
1.  En Visual Studio, abra el archivo **Default.aspx** bajo el proyecto **TestApp**.  
  
2.  Reemplace el marcado existente en el archivo **Default.aspx** con el siguiente marcado:  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  Guarde **Default.aspx** y abra su archivo de código subyacente **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** puede estar oculto bajo **Default.aspx** en el Explorador de soluciones.  Si **Default.aspx.cs** no está visible, expanda **Default.aspx** haciendo clic en el triángulo que se encuentra al lado.  
  
4.  Reemplace el código existente en **Default.aspx.cs** por el código siguiente:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  Guarde **Default.aspx.cs** y compile la aplicación.  
  
## Paso 5 \- Probar la integración entre WIF y la aplicación ASP.NET  
 Este paso describe cómo puede probar la integración entre WIF y la aplicación ASP.NET.  
  
#### Para probar la integración entre WIF y ASP.NET  
  
1.  En Visual Studio, presione **F5** para iniciar la depuración de la aplicación.  Si no se encuentra ningún error, se abrirá una nueva ventana del explorador.  
  
2.  Puede observar que el explorador redirige de manera silenciosa la solicitud al STS y abre a continuación la página Default.aspx.  Si WIF está configurado de manera adecuada, debería ver que el sitio muestra el texto siguiente: **“You are signed”** indicándole que ha iniciado sesión.