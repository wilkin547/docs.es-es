---
title: "C&#243;mo: compilar aplicaciones ASP.NET para notificaciones mediante la autenticaci&#243;n basada en formularios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# C&#243;mo: compilar aplicaciones ASP.NET para notificaciones mediante la autenticaci&#243;n basada en formularios
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   Formularios Web Forms de ASP.NET®  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para crear una aplicación demanda\- reconozca simple de formularios Web Forms de ASP.NET que utilice la autenticación de formularios.  También proporciona instrucciones sobre cómo probar la aplicación para comprobar que las peticiones se muestran cuando un usuario firma en con la autenticación de formularios.  
  
## Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- la aplicación de formularios Web Forms de Configurar ASP.NET para las peticiones Utilizar la autenticación  
  
-   Paso 3 \- pruebe la solución  
  
## Objetivos  
  
-   Configurar una aplicación de formularios Web Forms de ASP.NET para las peticiones mediante la autenticación de formularios  
  
-   Pruebe la aplicación de formularios Web Forms de ASP.NET para ver si funciona correctamente  
  
## Información general  
 En .NET 4,5, WIF y la autorización demanda\- basada se ha incluido como parte integrante del marco.  Anteriormente, si deseara peticiones de un usuario de ASP.NET, se requieren instalar WIF, y después convierte interfaces a los objetos de la entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`.  Ahora, las peticiones son ocupa automáticamente estos objetos de entidad de seguridad.  
  
 La autenticación de formularios se ha beneficiado include de WIF en .NET 4,5 porque todos los usuarios autenticados por los formularios automáticamente tienen peticiones asociadas a ellos.  Puede usar estas peticiones inmediatamente en una aplicación ASP.NET que utilice la autenticación de formularios, como en este procedimiento se muestran.  
  
## Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- la aplicación de formularios Web Forms de Configurar ASP.NET para las peticiones Utilizar la autenticación  
  
-   Paso 3 \- pruebe la solución  
  
## Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
 En este paso, creará una nueva aplicación de formularios Web Forms de ASP.NET.  
  
#### Para crear una aplicación ASP.NET simple  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo**y, a continuación **Proyecto**.  
  
2.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación de formularios Web Forms de ASP.NET**.  
  
3.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
## Paso 2 \- la aplicación de formularios Web Forms de Configurar ASP.NET para las peticiones Utilizar la autenticación  
 En este paso se agregará una entrada de configuración al archivo de configuración *Web.config* y editará el Default.aspxfile para mostrar la información de las peticiones de una cuenta.  
  
#### Para configurar la aplicación ASP.NET para las peticiones mediante la autenticación de formularios  
  
1.  En *el archivo Default.aspx* , reemplace el marcado existente con el siguiente:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
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
  
     Este paso agrega un control GridView a la *página Default.aspx* que se rellena con las demandas recuperadas de la autenticación de formularios.  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     El código anterior mostrará peticiones sobre un usuario autenticado, incluidos los usuarios identificados por la autenticación de formularios.  
  
## Paso 3 \- pruebe la solución  
 En este paso probará la aplicación de formularios Web Forms de ASP.NET, y comprueba que las peticiones se muestran cuando un usuario firma en con la autenticación de formularios.  
  
#### Para probar la aplicación de formularios Web Forms de ASP.NET para las peticiones mediante la autenticación de formularios  
  
1.  Presione **F5** para compilar y ejecutar la aplicación.  Debe mostrar con *Default.aspx, que*tiene **Registrar** y **Inicio de sesión** vínculos en la parte superior derecha de la página.  Haga clic en **Registrarse**.  
  
2.  En la página de **Registrar** , cree una cuenta de usuario, y haga clic en **Registrar**.  La cuenta se realizará utilizando la autenticación de formularios, y en automáticamente se firmarán.  
  
3.  Cuando se ha redirigido a la página principal, debería ver una tabla debajo de la dirección de **Las peticiones** que incluye **Emisor**, **OriginalIssuer**, **Tipo**, **Valor**, e información de las peticiones de **ValueType** sobre su cuenta.