---
title: Creación de un servicio WCF con AJAX habilitado y un cliente de ASP.NET en Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 0bfe55c68f68bfef7b7ec2034413b53d41b0c785
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609361"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio

En este tema se muestra cómo usar Visual Studio para crear un servicio de Windows Communication Foundation (WCF) habilitado para AJAX y un cliente de ASP.NET que tiene acceso al servicio.

## <a name="create-an-aspnet-web-app"></a>Creación de una aplicación web de ASP.NET

1. Abra Visual Studio.

1. En el menú **archivo** , seleccione **nuevo**  >  **proyecto** .

1. En el cuadro de diálogo **nuevo proyecto** , **Installed**expanda la  >  categoría Web de**Visual C#** instalado  >  **Web** y, a continuación, seleccione **aplicación Web de ASP.net (.NET Framework)**.

1. Asigne al proyecto el nombre **SandwichServices** y haga clic en **Aceptar**.

1. En el cuadro de diálogo **nueva aplicación Web de ASP.net** , seleccione **vacío** y, después, haga clic en **Aceptar**.

   ![Cuadro de diálogo de tipo de aplicación Web de ASP.NET en Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Agregar un formulario Web Forms

1. Haga clic con el botón derecho en el proyecto SandwichServices en **Explorador de soluciones** y seleccione **Agregar**  >  **nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento** , expanda la **Installed**  >  categoría Web de**Visual C#** instalado  >  **Web** y, a continuación, seleccione la plantilla de **formulario web** .

1. Acepte el nombre predeterminado (**WebForm1**) y, a continuación, seleccione **Agregar**.

   *WebForm1. aspx* se abre en la vista **código fuente** .

1. Agregue el siguiente marcado dentro de las **\<body>** Etiquetas:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Crear un servicio WCF habilitado para AJAX

1. Haga clic con el botón derecho en el proyecto SandwichServices en **Explorador de soluciones** y seleccione **Agregar**  >  **nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento** , expanda la **Installed**  >  categoría Web de**Visual C#** instalado  >  **Web** y, a continuación, seleccione la plantilla **servicio WCF (habilitado para Ajax)** .

   ![Plantilla de elementos de servicio WCF (AJAX habilitado) en Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Asigne al servicio el nombre **CostService** y, a continuación, seleccione **Agregar**.

   *CostService.SVC.CS* se abre en el editor.

1. Implemente la operación en el servicio. Agregue el método siguiente a la clase CostService para calcular el costo de una cantidad de bocadillos:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Configurar el cliente para tener acceso al servicio

1. Abra el archivo *WebForm1. aspx* y seleccione la vista de **diseño** .

2. En el menú **Ver** , seleccione **cuadro de herramientas**.

3. Expanda el nodo **extensiones Ajax** y arrastre y coloque un control **ScriptManager** en el formulario.

4. De nuevo en la vista **código fuente** , agregue el siguiente código entre las **\<ScriptManager>** etiquetas para especificar la ruta de acceso al servicio WCF:

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. Agregue el código para la función de JavaScript `Calculate()` . Coloque el código siguiente en la sección de **encabezado** del formulario web:

    ```html
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

   Este código llama al método de CostService para calcular el precio de tres sandwiches y, a continuación, muestra el resultado en el intervalo denominado **additionResult**.

## <a name="run-the-program"></a>Ejecución del programa

Asegúrese de que *WebForm1. aspx* tiene el foco y, a continuación, presione el botón **iniciar** para iniciar el cliente web. El botón tiene un triángulo verde y dice algo como **IIS Express (Microsoft Edge)**. O bien, puede presionar <kbd>F5</kbd>. Haga clic en el botón **precio de 3 sándwiches** para generar el resultado esperado de "3,75".

## <a name="example"></a>Ejemplo

El siguiente es el código completo del archivo *CostService.SVC.CS* :

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

A continuación se encuentra todo el contenido de la página *WebForm1. aspx* :

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
