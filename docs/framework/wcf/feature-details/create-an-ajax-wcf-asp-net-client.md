---
title: Crear un servicio WCF con AJAX habilitado y un cliente de ASP.NET en Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48024615"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio

En este tema se muestra cómo usar Visual Studio para crear un servicio de Windows Communication Foundation (WCF) con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio.

## <a name="create-an-aspnet-web-app"></a>Crear una aplicación web ASP.NET

1. Abra Visual Studio.

1. Desde el **archivo** menú, seleccione **New** > **proyecto**

1. En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione **aplicación Web ASP.NET (.NET Framework)**.

1. Denomine el proyecto **SandwichServices** y haga clic en **Aceptar**.

1. En el **nueva aplicación Web ASP.NET** cuadro de diálogo, seleccione **vacía** y, a continuación, seleccione **Aceptar**.

   ![Cuadro de diálogo de tipo de aplicación ASP.NET web en Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Agregue un formulario web

1. Haga clic en el proyecto SandwichServices en **el Explorador de soluciones** y seleccione **agregar** > **nuevo elemento**.

1. En el **Agregar nuevo elemento** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione el **formulario Web Forms** plantilla.

1. Acepte el nombre predeterminado (**WebForm1**) y, a continuación, seleccione **agregar**.

   *WebForm1.aspx* se abre en **origen** vista.

1. Agregue el siguiente marcado dentro de la  **\<cuerpo >** etiquetas:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Creación de un servicio WCF con AJAX habilitado

1. Haga clic en el proyecto SandwichServices en **el Explorador de soluciones** y seleccione **agregar** > **nuevo elemento**.

1. En el **Agregar nuevo elemento** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione el **servicio WCF (AJAX habilitado)** plantilla.

   ![Plantilla de elemento (compatible con AJAX) de servicio WCF en Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Nombre del servicio **CostService** y, a continuación, seleccione **agregar**.

   *CostService.svc.cs* se abre en el editor.

1. Implementar la operación en el servicio. Agregue el método siguiente a la clase CostService para calcular el costo de una cantidad de bocadillos:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Configurar el cliente para tener acceso al servicio

1. Abra el *WebForm1.aspx* de archivo y seleccione el **diseño** vista.

2. Desde el **vista** menú, seleccione **cuadro de herramientas**.

3. Expanda el **AJAX Extensions** nodo y arrastrar y colocar un **ScriptManager** hasta el formulario.

4. En el **origen** ver, agregue el siguiente código entre el  **\<ScriptManager >** etiquetas para especificar la ruta de acceso al servicio de WCF:

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. Agregue el código para la función de Javascript `Calculate()`. Coloque el código siguiente en el **head** sección del formulario web:

    ```javascript
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   Este código llama al método de CostService para calcular el precio de tres bocadillos y, a continuación, muestra el resultado en el intervalo denominado **additionResult**.

## <a name="run-the-program"></a>Ejecutar el programa

Asegúrese de que *WebForm1.aspx* tiene el foco y, a continuación, presione **iniciar** botón para iniciar el cliente web. El botón tiene un triángulo verde y dice algo parecido a **IIS Express (Microsoft Edge)**. O bien, puede presionar **F5**. Haga clic en el **precio de 3 bocadillos** botón para generar el resultado esperado de "3,75".

## <a name="example-code"></a>código de ejemplo

Siguiente es el código completo en el *CostService.svc.cs* archivo:

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

La siguiente es todo el contenido de la *WebForm1.aspx* página:

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
