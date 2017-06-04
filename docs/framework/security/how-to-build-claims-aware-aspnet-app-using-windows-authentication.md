---
title: "C&#243;mo: crear aplicaciones ASP.NET para notificaciones mediante la autenticaci&#243;n de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# C&#243;mo: crear aplicaciones ASP.NET para notificaciones mediante la autenticaci&#243;n de Windows
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   Formularios Web Forms de ASP.NET®  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para crear una aplicación demanda\- reconozca simple de formularios Web Forms de ASP.NET que utilice la autenticación de Windows.  También proporciona instrucciones sobre cómo probar la aplicación para comprobar que las peticiones se muestran cuando un usuario firma de utilizando la autenticación de Windows.  
  
## Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación de Windows de Usar las peticiones  
  
-   Paso 3 \- pruebe la solución  
  
## Objetivos  
  
-   Configurar una aplicación de formularios Web Forms de ASP.NET para las peticiones mediante la autenticación de Windows  
  
-   Pruebe la aplicación de formularios Web Forms de ASP.NET para ver si funciona correctamente  
  
## Información general  
 En .NET 4,5, WIF y la autorización demanda\- basada se ha incluido como parte integrante del marco.  Anteriormente, si deseara peticiones de un usuario de ASP.NET, se requieren instalar WIF, y después convierte interfaces a los objetos de la entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`.  Ahora, las peticiones son ocupa automáticamente estos objetos de entidad de seguridad.  
  
 La autenticación de Windows se ha beneficiado include de WIF en .NET 4,5 porque todos los usuarios autenticados por las credenciales de Windows automáticamente tienen peticiones asociadas a ellos.  Puede usar estas peticiones inmediatamente en una aplicación ASP.NET que utilice la autenticación de Windows, como en este procedimiento se muestran.  
  
## Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación de Windows de Usar las peticiones  
  
-   Paso 3 \- pruebe la solución  
  
## Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
 En este paso, creará una nueva aplicación de formularios Web Forms de ASP.NET.  
  
#### Para crear una aplicación ASP.NET simple  
  
1.  Inicie Visual Studio, haga clic en **Archivo**, **Nuevo**y, a continuación **Proyecto**.  
  
2.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación de formularios Web Forms de ASP.NET**.  
  
3.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
4.  Una vez creado el proyecto de **TestApp** , haga clic en **Explorador de soluciones**.  Las propiedades del proyecto aparecerán en el panel de **Propiedades** debajo de **Explorador de soluciones**.  Establezca la propiedad de **Autenticación de Windows** a **Habilitado**.  
  
    > [!WARNING]
    >  La autenticación de Windows está deshabilitada de forma predeterminada en nuevas aplicaciones ASP.NET, por lo que debe habilitarla manualmente.  
  
## Paso 2 \- aplicación de formularios Web Forms de Configurar ASP.NET para la autenticación de Windows de Usar las peticiones  
 En este paso se agregará una entrada de configuración al archivo de configuración*Web.config* y modificará el Default.aspxfile para mostrar la información de las peticiones de una cuenta.  
  
#### Para configurar la aplicación ASP.NET para las peticiones mediante la autenticación de Windows  
  
1.  En *el archivo Default.aspx del* proyecto de **TestApp** , reemplace el marcado existente con el siguiente:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
     Este paso agrega un control GridView a la *página Default.aspx* que se rellena con las demandas recuperadas de la autenticación de Windows.  
  
2.  Guarde el archivo *Default.aspx* , vuelva a abrir el código\- detrás de Default.aspx.cs denominado archivo.  Reemplace la existencia codificada con lo siguiente:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     El código anterior mostrará peticiones sobre un usuario autenticado.  
  
3.  Para cambiar el tipo de autenticación de la aplicación, modifique el bloque de **\<authentication\>** en la sección de **\<system.web\>** del archivo *Web.config* raíz del proyecto para que incluya únicamente la siguiente entrada de configuración:  
  
    ```  
    <authentication mode="Windows" />  
    ```  
  
4.  Finalmente, modifique el bloque de **\<authorization\>** en la sección de **\<system.web\>** del mismo *archivo web.config* para forzar la autenticación:  
  
    ```  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## Paso 3 \- pruebe la solución  
 En este paso probará la aplicación de formularios Web Forms de ASP.NET, y comprueba que las peticiones se muestran cuando un usuario firma en con la autenticación de Windows.  
  
#### Para probar la aplicación de formularios Web Forms de ASP.NET para las peticiones mediante la autenticación de Windows  
  
1.  Presione **F5** para compilar y ejecutar la aplicación.  Debe mostrar con *Default.aspx, y*su nombre de cuenta de Windows \(nombre de dominio incluidos\) debe aparecer ya como el usuario autenticado en el superior derecho de la página.  El contenido de la página debe incluir una tabla rellenada con las peticiones recuperadas de su cuenta de Windows.