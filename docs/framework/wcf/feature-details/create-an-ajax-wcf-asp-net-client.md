---
title: Creación de un servicio WCF con AJAX habilitado y un cliente de ASP.NET en Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: a6d6e87de6200a5cb9bba566d595066673cdf9cf
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834791"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="d3be2-102">Procedimiento Crear un servicio WCF habilitado para AJAX y un cliente de ASP.NET que tenga acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="d3be2-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="d3be2-103">En este tema se muestra cómo usar Visual Studio para crear un servicio de Windows Communication Foundation (WCF) habilitado para AJAX y un cliente de ASP.NET que tiene acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="d3be2-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="d3be2-104">Crear una aplicación web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d3be2-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="d3be2-105">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3be2-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="d3be2-106">En el menú **archivo** , seleccione **nuevo** > **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="d3be2-107">En el cuadro de diálogo **nuevo proyecto** , > expanda la categoría  >  **Web** **Visual C#** instalada y, a continuación, seleccione **aplicación Web de ASP.net (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="d3be2-108">Asigne al proyecto el nombre **SandwichServices** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="d3be2-109">En el cuadro de diálogo **nueva aplicación Web de ASP.net** , seleccione **vacío** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Cuadro de diálogo de tipo de aplicación Web de ASP.NET en Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="d3be2-111">Agregar un formulario Web Forms</span><span class="sxs-lookup"><span data-stu-id="d3be2-111">Add a web form</span></span>

1. <span data-ttu-id="d3be2-112">Haga clic con el botón derecho en el proyecto SandwichServices en **Explorador de soluciones** y seleccione **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d3be2-113">En el cuadro de diálogo **Agregar nuevo elemento** , > expanda la categoría  >  **Web** **Visual C#** instalada y, a continuación, seleccione la plantilla de **formulario web** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="d3be2-114">Acepte el nombre predeterminado (**WebForm1**) y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="d3be2-115">*WebForm1. aspx* se abre en la vista **código fuente** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="d3be2-116">Agregue el siguiente marcado dentro del  **\<cuerpo >** Etiquetas:</span><span class="sxs-lookup"><span data-stu-id="d3be2-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="d3be2-117">Crear un servicio WCF habilitado para AJAX</span><span class="sxs-lookup"><span data-stu-id="d3be2-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="d3be2-118">Haga clic con el botón derecho en el proyecto SandwichServices en **Explorador de soluciones** y seleccione **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d3be2-119">En el cuadro de diálogo **Agregar nuevo elemento** , > expanda la categoría **Web**  > **C#visual**instalada y, a continuación, seleccione la plantilla **servicio WCF (habilitado para Ajax)** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Plantilla de elementos de servicio WCF (AJAX habilitado) en Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="d3be2-121">Asigne al servicio el nombre **CostService** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="d3be2-122">*CostService.SVC.CS* se abre en el editor.</span><span class="sxs-lookup"><span data-stu-id="d3be2-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="d3be2-123">Implemente la operación en el servicio.</span><span class="sxs-lookup"><span data-stu-id="d3be2-123">Implement the operation in the service.</span></span> <span data-ttu-id="d3be2-124">Agregue el método siguiente a la clase CostService para calcular el costo de una cantidad de bocadillos:</span><span class="sxs-lookup"><span data-stu-id="d3be2-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="d3be2-125">Configurar el cliente para tener acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="d3be2-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="d3be2-126">Abra el archivo *WebForm1. aspx* y seleccione la vista de **diseño** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="d3be2-127">En el menú **Ver** , seleccione **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="d3be2-128">Expanda el nodo **extensiones Ajax** y arrastre y coloque un control **ScriptManager** en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d3be2-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="d3be2-129">De nuevo en la vista **código fuente** , agregue el siguiente código entre las  **\<etiquetas ScriptManager >** para especificar la ruta de acceso al servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="d3be2-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="d3be2-130">Agregue el código para la función `Calculate()`de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="d3be2-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="d3be2-131">Coloque el código siguiente en la sección de **encabezado** del formulario web:</span><span class="sxs-lookup"><span data-stu-id="d3be2-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="d3be2-132">Este código llama al método de CostService para calcular el precio de tres sandwiches y, a continuación, muestra el resultado en el intervalo denominado **additionResult**.</span><span class="sxs-lookup"><span data-stu-id="d3be2-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="d3be2-133">Ejecutar el programa</span><span class="sxs-lookup"><span data-stu-id="d3be2-133">Run the program</span></span>

<span data-ttu-id="d3be2-134">Asegúrese de que *WebForm1. aspx* tiene el foco y, a continuación, presione el botón **iniciar** para iniciar el cliente web.</span><span class="sxs-lookup"><span data-stu-id="d3be2-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="d3be2-135">El botón tiene un triángulo verde y dice algo como **IIS Express (Microsoft Edge)** .</span><span class="sxs-lookup"><span data-stu-id="d3be2-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="d3be2-136">O bien, puede presionar <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d3be2-136">Or, you can press <kbd>F5</kbd>.</span></span> <span data-ttu-id="d3be2-137">Haga clic en el botón **precio de 3 sándwiches** para generar el resultado esperado de "3,75".</span><span class="sxs-lookup"><span data-stu-id="d3be2-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example"></a><span data-ttu-id="d3be2-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3be2-138">Example</span></span>

<span data-ttu-id="d3be2-139">El siguiente es el código completo del archivo *CostService.SVC.CS* :</span><span class="sxs-lookup"><span data-stu-id="d3be2-139">The following is the full code in the *CostService.svc.cs* file:</span></span>

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

<span data-ttu-id="d3be2-140">A continuación se encuentra todo el contenido de la página *WebForm1. aspx* :</span><span class="sxs-lookup"><span data-stu-id="d3be2-140">The following is the full contents of the *WebForm1.aspx* page:</span></span>

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
