---
title: 'Cómo: crear aplicaciones ASP.NET para notificaciones mediante la autenticación de Windows'
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 2c7877c452c729b30029cad1a8e17600f3dc9661
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198533"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a>Cómo: crear aplicaciones ASP.NET para notificaciones mediante la autenticación de Windows
## <a name="applies-to"></a>Se aplica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Formularios Web Forms ASP.NET®  
  
## <a name="summary"></a>Resumen  
 Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones que usa la autenticación de Windows. También proporciona instrucciones para probar la aplicación para comprobar que las notificaciones se presentan cuando un usuario inicia sesión con la autenticación de Windows.  
  
## <a name="contents"></a>Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
-   Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows  
  
-   Paso 3: Probar la solución  
  
## <a name="objectives"></a>Objetivos  
  
-   Configurar una aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows  
  
-   Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente  
  
## <a name="overview"></a>Información general  
 En .NET 4.5, WIF y su autorización basada en notificaciones se han incluido como parte integral del marco. Anteriormente, si quería notificaciones de un usuario de ASP.NET, tenía que instalar WIF y, después, convertir las interfaces a objetos de entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`. Ahora, estos objetos de entidad de seguridad sirven las notificaciones automáticamente.  
  
 La autenticación de Windows se ha beneficiado de la inclusión de WIF en .NET 4.5, ya que todos los usuarios autenticados mediante credenciales de Windows automáticamente tienen notificaciones asociadas. Puede empezar a usar estas notificaciones inmediatamente en una aplicación de ASP.NET que use la autenticación de Windows, como se muestra en este tema de procedimientos.  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
-   Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows  
  
-   Paso 3: Probar la solución  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
 En este paso creará una aplicación de formularios Web Forms ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla  
  
1.  Inicie Visual Studio y, después, haga clic en **Archivo**, **Nuevo** y en **Proyecto**.  
  
2.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
3.  En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
4.  Después de que se haya creado el proyecto **TestApp**, haga clic en él en el **Explorador de soluciones**. Las propiedades del proyecto aparecerán en el panel **Propiedades** debajo del **Explorador de soluciones**. Establezca la propiedad **Autenticación de Windows** en **Habilitado**.  
  
    > [!WARNING]
    >  La autenticación de Windows está deshabilitada de manera predeterminada en las nuevas aplicaciones ASP.NET, por lo que debe habilitarla manualmente.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows  
 En este paso agregará una entrada de configuración al archivo de configuración *Web.config* y modificará el archivo *Default.aspx* para que se muestre la información de notificaciones de una cuenta.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a>Para configurar la aplicación ASP.NET para notificaciones mediante la autenticación de Windows  
  
1.  En el archivo *Default.aspx* del proyecto **TestApp**, reemplace el marcado existente por el siguiente:  
  
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
  
     Este paso agrega un control GridView a la página *Default.aspx* que se va a rellenar con las notificaciones recuperadas de la autenticación de Windows.  
  
2.  Guarde el archivo *Default.aspx* y abra su archivo de código subyacente denominado *Default.aspx.cs*. Reemplace el código existente por el siguiente:  
  
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
  
     El código anterior mostrará las notificaciones sobre un usuario autenticado.  
  
3.  Para cambiar el tipo de autenticación de la aplicación, modifique el bloque **\<authentication>** en la sección **\<system.web>** del archivo *Web.config* de la raíz del proyecto, de manera que solo incluya la siguiente entrada de configuración:  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  Por último, modifique el bloque **\<authorization>** en la sección **\<system.web>** del mismo archivo *Web.config* para forzar la autenticación:  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a>Paso 3: Probar la solución  
 En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de Windows.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows  
  
1.  Presione **F5** para compilar y ejecutar la aplicación. Debe aparecer con *Default.aspx*, y su nombre de cuenta Windows (incluido el nombre de dominio) ya debe aparecer como el usuario autenticado en la parte superior derecha de la página. El contenido de la página debe incluir una tabla en la que aparecen las notificaciones que se han recuperado de su cuenta Windows.
