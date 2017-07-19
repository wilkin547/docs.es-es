---
title: "C&#243;mo: transformar las notificaciones entrantes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# C&#243;mo: transformar las notificaciones entrantes
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   Formularios Web Forms de ASP.NET®  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para crear una aplicación demanda\- reconozca simple de formularios Web Forms de ASP.NET y transformar peticiones de entrada.  También proporciona instrucciones sobre cómo probar la aplicación para comprobar que las peticiones transformadas se muestran cuando se ejecuta la aplicación.  
  
## Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- la implementación petición transformación Utilizar un ClaimsAuthenticationManager personalizado  
  
-   Paso 3 \- pruebe la solución  
  
## Objetivos  
  
-   Configurar una aplicación de formularios Web Forms de ASP.NET para la autenticación demanda\- basada  
  
-   Modifique las peticiones de entrada agregando un rol de administrador de petición  
  
-   Pruebe la aplicación de formularios Web Forms de ASP.NET para ver si funciona correctamente  
  
## Información general  
 WIF expone una clase denominada <xref:System.Security.Claims.ClaimsAuthenticationManager> que permite a los usuarios modificar peticiones antes de que se muestran a una aplicación de \(RP\) de usuario de confianza.  <xref:System.Security.Claims.ClaimsAuthenticationManager> es útil para la separación de aspectos entre authentication y el código de aplicación subyacente.  El ejemplo siguiente muestra cómo agregar un rol a las peticiones en <xref:System.Security.Claims.ClaimsPrincipal> de entrada que se puede requerir el RP.  
  
## Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
  
-   Paso 2 \- la implementación petición transformación Utilizar un ClaimsAuthenticationManager personalizado  
  
-   Paso 3 \- pruebe la solución  
  
## Paso 1 \- cree una aplicación de formularios Web Forms de ASP.NET Simple  
 En este paso, creará una nueva aplicación de formularios Web Forms de ASP.NET.  
  
#### Para crear una aplicación ASP.NET simple  
  
1.  Inicie Visual Studio en modo elevado como administrador.  
  
2.  En Visual Studio, haga clic **Archivo**, haga clic **Nuevo**, y haga clic en **Proyecto**.  
  
3.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación de formularios Web Forms de ASP.NET**.  
  
4.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
5.  Haga clic con el botón secundario en el proyecto de **TestApp** en **Explorador de soluciones**, seleccione **identidad y Access**.  
  
6.  La ventana de **identidad y Access** aparece.  En **Proveedores**, seleccione **Pruebe la aplicación con el desarrollo local STS**, haga clic en **Aplicar**.  
  
7.  En *el archivo Default.aspx* , reemplace el marcado existente con el siguiente, guarde el archivo:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
8.  Abra código\-detrás de *Default.aspx.cs*denominado archivo.  Reemplace la existencia codificada con el siguiente, guarde el archivo:  
  
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
  
## Paso 2 \- la implementación petición transformación Utilizar un ClaimsAuthenticationManager personalizado  
 En este paso se reemplazará funcionalidad predeterminada en la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> para agregar un rol de administrador a la entidad de seguridad de entrada.  
  
#### Para implementar la transformación de las peticiones mediante un ClaimsAuthenticationManager personalizado  
  
1.  En Visual Studio, haga clic con el botón secundario en la solución, haga clic en **Agregar**, y haga clic en **Nuevo proyecto**.  
  
2.  En la ventana de **Agregar nuevo proyecto** , **Biblioteca de clases** seleccione de la lista de plantillas de **Visual C\#** , entra en `ClaimsTransformation`, y presione **Aceptar**.  El nuevo proyecto se creará en la carpeta de la solución.  
  
3.  Haga clic con el botón secundario en **Referencias** bajo el proyecto de **ClaimsTransformation** , y haga clic en **Agregar referencia**.  
  
4.  En la ventana de **Administrador de referencias** , **System.IdentityModel**seleccione, y haga clic en **Aceptar**.  
  
5.  Abra **Class1.cs**, o si no existe, haga clic con **ClaimsTransformation**, haga clic en **Agregar**, haga clic en **Ordenar…**  
  
6.  Agregue las siguientes directivas using al archivo de código:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Agregue la clase y el método siguientes en el archivo de código.  
  
    > [!WARNING]
    >  El código siguiente es la demostración sólo; asegúrese de comprobar los permisos deseados en código de producción.  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  Guarde el archivo y compilar el proyecto de **ClaimsTransformation** .  
  
9. En el proyecto de **TestApp** ASP.NET, haga clic con el botón secundario en referencias, y haga clic en **Agregar referencia**.  
  
10. En la ventana de **Administrador de referencias** , **Solución** seleccione en el menú izquierdo, **ClaimsTransformation** seleccionar entre las opciones rellenas, y haga clic en **Aceptar**.  
  
11. En el archivo de **Web.config** raíz, navegue a la entrada de **\<system.identityModel\>** .  Dentro de los elementos de **\<identityConfiguration\>** , agregue la línea siguiente y guarde el archivo:  
  
    ```  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## Paso 3 \- pruebe la solución  
 En este paso probará la aplicación de formularios Web Forms de ASP.NET, y comprueba que las peticiones se muestran cuando un usuario firma en con la autenticación de formularios.  
  
#### Para probar la aplicación de formularios Web Forms de ASP.NET para las peticiones mediante la autenticación de formularios  
  
1.  Presione **F5** para compilar y ejecutar la aplicación.  Debe mostrar con *Default.aspx.*  
  
2.  En *la página Default.aspx* , debería ver una tabla debajo de la dirección de **Las peticiones** que incluye **Emisor**, **OriginalIssuer**, **Tipo**, **Valor**, e información de las peticiones de **ValueType** sobre su cuenta.  La última fila se debería mostrar así:  
  
    ||||||  
    |-|-|-|-|-|  
    |CUENTA LOCAL|CUENTA LOCAL|http:\/\/schemas.microsoft.com\/ws\/2008\/06\/identity\/claims\/role|Admin|http:\/\/www.w3.org\/2001\/XMLSchema\#string|