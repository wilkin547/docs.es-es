---
title: Cómo compilar aplicaciones ASP.NET con reconocimiento de mediante la autenticación basada en formularios
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: 75db96a621d7863ef445efb24814111b34da6960
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971834"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a>Cómo compilar aplicaciones ASP.NET con reconocimiento de mediante la autenticación basada en formularios

## <a name="applies-to"></a>Se aplica a

- Microsoft® Windows® Identity Foundation (WIF)

- Formularios Web Forms ASP.NET®

## <a name="summary"></a>Resumen

Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones que usa la autenticación de formularios. También proporciona instrucciones para probar la aplicación a fin de comprobar que las notificaciones se presentan cuando un usuario inicia sesión con la autenticación de formularios.

## <a name="contents"></a>Contenido

- Objetivos

- Información general

- Resumen de pasos

- Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET

- Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios

- Paso 3: Probar la solución

## <a name="objectives"></a>Objetivos

- Configurar una aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios

- Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente

## <a name="overview"></a>Información general

En .NET 4.5, WIF y su autorización basada en notificaciones se han incluido como parte integral del marco. Anteriormente, si quería notificaciones de un usuario de ASP.NET, tenía que instalar WIF y, después, convertir las interfaces a objetos de entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`. Ahora, estos objetos de entidad de seguridad sirven las notificaciones automáticamente.

La autenticación de formularios se ha beneficiado de la inclusión de WIF en .NET 4.5, ya que todos los usuarios autenticados mediante formularios automáticamente tienen notificaciones asociadas. Puede empezar a usar estas notificaciones inmediatamente en una aplicación de ASP.NET que use la autenticación de formularios, como se muestra en este tema de procedimientos.

## <a name="summary-of-steps"></a>Resumen de pasos

- Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET

- Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios

- Paso 3: Probar la solución

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET

En este paso creará una aplicación de formularios Web Forms ASP.NET.

### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla

1. Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.

2. En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.

3. En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.

## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios

En este paso se agrega una entrada de configuración al archivo de configuración *Web.config* y se edita el archivo *Default.aspx* para que muestre la información de notificaciones de una cuenta.

### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a>Para configurar la aplicación ASP.NET para notificaciones mediante la autenticación de formularios

1. En el archivo *Default.aspx*, reemplace el marcado existente por el siguiente:

    ```aspx
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

    Este paso agrega un control GridView a la página *Default.aspx* que se va a rellenar con las notificaciones recuperadas de la autenticación de formularios.

2. Guarde el archivo *Default.aspx* y abra su archivo de código subyacente denominado *Default.aspx.cs*. Reemplace el código existente por el siguiente:

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

    El código anterior muestra notificaciones sobre un usuario autenticado, incluidos los usuarios identificados mediante la autenticación de formularios.

## <a name="step-3--test-your-solution"></a>Paso 3: Probar la solución

En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de formularios.

### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios

1. Presione **F5** para compilar y ejecutar la aplicación. Debe aparecer *Default.aspx*, que tiene los vínculos **Registrarse** e **Iniciar sesión** en la parte superior derecha de la página. Haga clic en **Registrarse**.

2. En la página **Registrarse**, cree una cuenta de usuario y luego haga clic en **Registrarse**. Se crea la cuenta mediante la autenticación de formularios y la sesión se inicia automáticamente.

3. Después de que se le haya redirigido a la página principal, debería ver una tabla debajo del título **Sus notificaciones** con la información de notificaciones **Emisor**, **OriginalIssuer**, **Tipo**, **Valor** y **ValueType** sobre la cuenta.
