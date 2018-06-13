---
title: Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio
ms.date: 03/30/2017
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 58971d11ab76112627dd81d53381236932268e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490635"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="a147e-102">Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="a147e-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="a147e-103">Este tema muestra cómo utilizar Visual Studio 2008 para crear un servicio de Windows Communication Foundation (WCF) con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="a147e-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="a147e-104">El código para el servicio y para el cliente se proporciona en la sección Ejemplo después de que los pasos para crearlos se describan en la sección Procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a147e-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="a147e-105">Para crear la aplicación cliente de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a147e-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="a147e-106">Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a147e-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="a147e-107">Desde el **archivo** menú, seleccione **nuevo**, a continuación, **proyecto**, a continuación, **Web**y, a continuación, seleccione **aplicación Web de ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="a147e-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="a147e-108">Denomine el proyecto `SandwichServices` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a147e-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="a147e-109">Para crear el servicio WCF con AJAX habilitado</span><span class="sxs-lookup"><span data-stu-id="a147e-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="a147e-110">Haga clic en el `SandwichServices` del proyecto en el **el Explorador de soluciones** ventana y seleccione **agregar**, a continuación, **nuevo elemento**y, a continuación, **servicio de WCF con AJAX habilitado** .</span><span class="sxs-lookup"><span data-stu-id="a147e-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="a147e-111">El servicio de nombres `CostService` en el **nombre** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="a147e-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="a147e-112">Abra el archivo CostService.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="a147e-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="a147e-113">Especifique el `Namespace` para <xref:System.ServiceModel.ServiceContractAttribute> como `SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="a147e-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  <span data-ttu-id="a147e-114">Implemente las operaciones en el servicio.</span><span class="sxs-lookup"><span data-stu-id="a147e-114">Implement the operations in the service.</span></span> <span data-ttu-id="a147e-115">Agregue <xref:System.ServiceModel.OperationContractAttribute> a cada una de las operaciones para indicar que forman parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="a147e-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="a147e-116">El ejemplo siguiente implementa un método que devuelve el costo de una cantidad determinada de bocadillos.</span><span class="sxs-lookup"><span data-stu-id="a147e-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="a147e-117">Configurar el cliente para obtener acceso al servicio</span><span class="sxs-lookup"><span data-stu-id="a147e-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="a147e-118">Abra la página Default.aspx y seleccione el **diseño** vista.</span><span class="sxs-lookup"><span data-stu-id="a147e-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="a147e-119">Desde el **vista** menú, seleccione **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="a147e-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="a147e-120">Expanda el **extensiones AJAX** nodo y arrastre y coloque una **ScriptManager** en la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="a147e-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="a147e-121">Haga clic en el **ScriptManager** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a147e-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="a147e-122">Expanda el **servicios** colección en la **propiedades** ventana para abrir la **Editor de colecciones ServiceReference** ventana.</span><span class="sxs-lookup"><span data-stu-id="a147e-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="a147e-123">Haga clic en **agregar**, especifique `CostService.svc` como el **ruta de acceso** hace referencia a y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a147e-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="a147e-124">Expanda el **HTML** nodo en el **cuadro de herramientas** y arrastre y coloque una **entrada (botón)** en la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="a147e-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="a147e-125">Haga clic en el **botón** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a147e-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="a147e-126">Cambiar el **valor** campo `Price for 3 Sandwiches`.</span><span class="sxs-lookup"><span data-stu-id="a147e-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="a147e-127">Haga doble clic en el **botón** para acceder al código de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="a147e-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="a147e-128">Pasar en el siguiente código de JavaScript en el <`script`> elemento.</span><span class="sxs-lookup"><span data-stu-id="a147e-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="a147e-129">Obtener acceso al servicio desde el cliente</span><span class="sxs-lookup"><span data-stu-id="a147e-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="a147e-130">Utilice Ctrl + F5 para iniciar el servicio y el cliente web.</span><span class="sxs-lookup"><span data-stu-id="a147e-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="a147e-131">Haga clic en el **precio de 3 bocadillos a la parrilla** botón para generar el resultado esperado de "3,75".</span><span class="sxs-lookup"><span data-stu-id="a147e-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="a147e-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a147e-132">Example</span></span>  
 <span data-ttu-id="a147e-133">Este ejemplo contiene el código del servicio contenido en el archivo WCFService.svc.cs y el código de cliente contenido en el archivo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="a147e-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     
