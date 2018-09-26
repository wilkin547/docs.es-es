---
title: 'Cómo: transformar las notificaciones entrantes'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: 8673b4520d9727ae1aa78ef0bc9f435defb02598
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171327"
---
# <a name="how-to-transform-incoming-claims"></a>Cómo: transformar las notificaciones entrantes
## <a name="applies-to"></a>Se aplica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Formularios Web Forms ASP.NET®  
  
## <a name="summary"></a>Resumen  
 Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones y transformar las notificaciones entrantes. También se proporcionan instrucciones sobre cómo probar la aplicación para comprobar que las notificaciones transformadas están presentes cuando se ejecuta la aplicación.  
  
## <a name="contents"></a>Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
-   Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado  
  
-   Paso 3: Probar la solución  
  
## <a name="objectives"></a>Objetivos  
  
-   Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones  
  
-   Transformar las notificaciones entrantes agregando una notificación de rol de administrador  
  
-   Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente  
  
## <a name="overview"></a>Información general  
 WIF expone una clase denominada <xref:System.Security.Claims.ClaimsAuthenticationManager> que permite a los usuarios modificar notificaciones antes de que se presenten en una aplicación de usuario de confianza (RP). <xref:System.Security.Claims.ClaimsAuthenticationManager> es útil para la separación de intereses entre la autenticación y el código de la aplicación subyacente. En el ejemplo siguiente se muestra cómo agregar un rol a las notificaciones en la <xref:System.Security.Claims.ClaimsPrincipal> entrante que el RP puede necesitar.  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
-   Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
  
-   Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado  
  
-   Paso 3: Probar la solución  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET  
 En este paso creará una aplicación de formularios Web Forms ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla  
  
1.  Inicie Visual Studio como administrador con permisos elevados.  
  
2.  En Visual Studio, haga clic en **Archivo**, en **Nuevo** y, después, en **Proyecto**.  
  
3.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
4.  En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
5.  Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.  
  
6.  Aparecerá la ventana **Identity and Access**. En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.  
  
7.  En el archivo *Default.aspx*, reemplace el marcado existente por el siguiente, después guarde el archivo:  
  
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
  
8.  Abra el archivo de código subyacente denominado *Default.aspx.cs*. Reemplace el código existente por el siguiente y, después, guarde el archivo:  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado  
 En este paso reemplazará la función predeterminada en la clase <xref:System.Security.Claims.ClaimsAuthenticationManager> para agregar un rol de administrador a la entidad de seguridad entrante.  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Para implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado  
  
1.  En Visual Studio, haga clic con el botón derecho en la solución, haga clic en **Agregar** y, después, en **Nuevo proyecto**.  
  
2.  En la ventana **Agregar nuevo proyecto**, seleccione **Biblioteca de clases** en la lista de plantillas de **Visual C#**, escriba `ClaimsTransformation` y pulse **Aceptar**. El nuevo proyecto se creará en la carpeta de la solución.  
  
3.  Haga clic con el botón derecho en **Referencias** debajo del proyecto **ClaimsTransformation** y, después, haga clic en **Agregar referencia**.  
  
4.  En la ventana **Administrador de referencias**, seleccione **System.IdentityModel** y, después, haga clic en **Aceptar**.  
  
5.  Abra **Class1.cs**, o si no existe, haga clic con el botón derecho en **ClaimsTransformation**, en **Agregar** y, después, en **Clase...**  
  
6.  Agregue lo siguiente mediante las directivas al archivo de código:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Agregue la siguiente clase y método en el archivo de código.  
  
    > [!WARNING]
    >  El código siguiente se muestra solo con fines demostrativos; asegúrese de que comprueba sus permisos previstos en el código de producción.  
  
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
  
8.  Guarde el archivo y compile el proyecto **ClaimsTransformation**.  
  
9. En su proyecto de ASP.NET **TestApp**, haga clic con el botón derecho en Referencias y, después, haga clic en **Agregar referencias**.  
  
10. En la ventana **Administrador de referencias**, seleccione **Solución** del menú de la izquierda, seleccione **ClaimsTransformation** de las opciones que aparecen y, después, haga clic en **Aceptar**.  
  
11. En el archivo **Web.config** raíz, vaya a la entrada **\<system.identityModel>**. Dentro de los elementos **\<identityConfiguration>**, agregue la línea siguiente y guarde el archivo:  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a>Paso 3: Probar la solución  
 En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de formularios.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios  
  
1.  Presione **F5** para compilar y ejecutar la aplicación. Debe estar presente con *Default.aspx*.  
  
2.  En la página *Default.aspx*, debería ver una tabla debajo del título **Sus notificaciones** con la información de notificaciones **Emisor**, **OriginalIssuer**, **Tipo**, **Valor** y **ValueType** sobre la cuenta. La última fila debe estar presente de la manera siguiente:  
  
    ||||||  
    |-|-|-|-|-|  
    |LOCAL AUTHORITY|LOCAL AUTHORITY|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|Admin|http://www.w3.org/2001/XMLSchema#string|
