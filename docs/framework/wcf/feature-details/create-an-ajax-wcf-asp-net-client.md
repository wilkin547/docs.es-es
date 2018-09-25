---
title: Crear un servicio WCF con AJAX habilitado y un cliente de ASP.NET en Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080971"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="e43aa-102">Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="e43aa-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="e43aa-103">En este tema se muestra cómo usar Visual Studio para crear un servicio de Windows Communication Foundation (WCF) con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="e43aa-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="e43aa-104">Crear una aplicación web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e43aa-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="e43aa-105">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e43aa-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="e43aa-106">Desde el **archivo** menú, seleccione **New** > **proyecto**</span><span class="sxs-lookup"><span data-stu-id="e43aa-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="e43aa-107">En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione **aplicación Web ASP.NET (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="e43aa-108">Denomine el proyecto **SandwichServices** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="e43aa-109">En el **nueva aplicación Web ASP.NET** cuadro de diálogo, seleccione **vacía** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Cuadro de diálogo de tipo de aplicación ASP.NET web en Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="e43aa-111">Agregue un formulario web</span><span class="sxs-lookup"><span data-stu-id="e43aa-111">Add a web form</span></span>

1. <span data-ttu-id="e43aa-112">Haga clic en el proyecto SandwichServices en **el Explorador de soluciones** y seleccione **agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="e43aa-113">En el **Agregar nuevo elemento** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione el **formulario Web Forms** plantilla.</span><span class="sxs-lookup"><span data-stu-id="e43aa-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="e43aa-114">Acepte el nombre predeterminado (**WebForm1**) y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="e43aa-115">*WebForm1.aspx* se abre en **origen** vista.</span><span class="sxs-lookup"><span data-stu-id="e43aa-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="e43aa-116">Agregue el siguiente marcado dentro de la  **\<cuerpo >** etiquetas:</span><span class="sxs-lookup"><span data-stu-id="e43aa-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="e43aa-117">Creación de un servicio WCF con AJAX habilitado</span><span class="sxs-lookup"><span data-stu-id="e43aa-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="e43aa-118">Haga clic en el proyecto SandwichServices en **el Explorador de soluciones** y seleccione **agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="e43aa-119">En el **Agregar nuevo elemento** cuadro de diálogo, expanda el **instalado** > **Visual C#** > **Web** categoría y, a continuación, Seleccione el **servicio WCF (AJAX habilitado)** plantilla.</span><span class="sxs-lookup"><span data-stu-id="e43aa-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Plantilla de elemento (compatible con AJAX) de servicio WCF en Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="e43aa-121">Nombre del servicio **CostService** y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="e43aa-122">*CostService.svc.cs* se abre en el editor.</span><span class="sxs-lookup"><span data-stu-id="e43aa-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="e43aa-123">Implementar la operación en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e43aa-123">Implement the operation in the service.</span></span> <span data-ttu-id="e43aa-124">Agregue el método siguiente a la clase CostService para calcular el costo de una cantidad de bocadillos:</span><span class="sxs-lookup"><span data-stu-id="e43aa-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="e43aa-125">Configurar el cliente para tener acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="e43aa-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="e43aa-126">Abra el *WebForm1.aspx* de archivo y seleccione el **diseño** vista.</span><span class="sxs-lookup"><span data-stu-id="e43aa-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="e43aa-127">Desde el **vista** menú, seleccione **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="e43aa-128">Expanda el **AJAX Extensions** nodo y arrastrar y colocar un **ScriptManager** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="e43aa-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="e43aa-129">En el **origen** ver, agregue el siguiente código entre el  **\<ScriptManager >** etiquetas para especificar la ruta de acceso al servicio de WCF:</span><span class="sxs-lookup"><span data-stu-id="e43aa-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. <span data-ttu-id="e43aa-130">Agregue el código para la función de Javascript `Calculate()`.</span><span class="sxs-lookup"><span data-stu-id="e43aa-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="e43aa-131">Coloque el código siguiente en el **head** sección del formulario web:</span><span class="sxs-lookup"><span data-stu-id="e43aa-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="e43aa-132">Este código llama al método de CostService para calcular el precio de tres bocadillos y, a continuación, muestra el resultado en el intervalo denominado **additionResult**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="e43aa-133">Ejecutar el programa</span><span class="sxs-lookup"><span data-stu-id="e43aa-133">Run the program</span></span>

<span data-ttu-id="e43aa-134">Asegúrese de que *WebForm1.aspx* tiene el foco y, a continuación, presione **iniciar** botón para iniciar el cliente web.</span><span class="sxs-lookup"><span data-stu-id="e43aa-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="e43aa-135">El botón tiene un triángulo verde y dice algo parecido a **IIS Express (Microsoft Edge)**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="e43aa-136">O bien, puede presionar **F5**.</span><span class="sxs-lookup"><span data-stu-id="e43aa-136">Or, you can press **F5**.</span></span> <span data-ttu-id="e43aa-137">Haga clic en el **precio de 3 bocadillos** botón para generar el resultado esperado de "3,75".</span><span class="sxs-lookup"><span data-stu-id="e43aa-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="e43aa-138">código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e43aa-138">Example code</span></span>

<span data-ttu-id="e43aa-139">Siguiente es el código completo en el *CostService.svc.cs* archivo:</span><span class="sxs-lookup"><span data-stu-id="e43aa-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

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

<span data-ttu-id="e43aa-140">La siguiente es todo el contenido de la *WebForm1.aspx* página:</span><span class="sxs-lookup"><span data-stu-id="e43aa-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

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
