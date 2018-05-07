---
title: Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio
ms.date: 03/30/2017
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 58971d11ab76112627dd81d53381236932268e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Cómo crear un servicio WFC con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio
Este tema muestra cómo utilizar Visual Studio 2008 para crear un servicio de Windows Communication Foundation (WCF) con AJAX habilitado y un cliente ASP.NET que tiene acceso al servicio. El código para el servicio y para el cliente se proporciona en la sección Ejemplo después de que los pasos para crearlos se describan en la sección Procedimientos.  
  
### <a name="to-create-the-aspnet-client-application"></a>Para crear la aplicación cliente de ASP.NET  
  
1.  Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Desde el **archivo** menú, seleccione **nuevo**, a continuación, **proyecto**, a continuación, **Web**y, a continuación, seleccione **aplicación Web de ASP.NET**.  
  
3.  Denomine el proyecto `SandwichServices` y haga clic en **Aceptar**.  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a>Para crear el servicio WCF con AJAX habilitado  
  
1.  Haga clic en el `SandwichServices` del proyecto en el **el Explorador de soluciones** ventana y seleccione **agregar**, a continuación, **nuevo elemento**y, a continuación, **servicio de WCF con AJAX habilitado** .  
  
2.  El servicio de nombres `CostService` en el **nombre** y haga clic en **agregar**.  
  
3.  Abra el archivo CostService.svc.cs.  
  
4.  Especifique el `Namespace` para <xref:System.ServiceModel.ServiceContractAttribute> como `SandwichService`:  
  
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
  
5.  Implemente las operaciones en el servicio. Agregue <xref:System.ServiceModel.OperationContractAttribute> a cada una de las operaciones para indicar que forman parte del contrato. El ejemplo siguiente implementa un método que devuelve el costo de una cantidad determinada de bocadillos.  
  
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
  
### <a name="to-configure-the-client-to-access-the-service"></a>Configurar el cliente para obtener acceso al servicio  
  
1.  Abra la página Default.aspx y seleccione el **diseño** vista.  
  
2.  Desde el **vista** menú, seleccione **cuadro de herramientas**.  
  
3.  Expanda el **extensiones AJAX** nodo y arrastre y coloque una **ScriptManager** en la página Default.aspx.  
  
4.  Haga clic en el **ScriptManager** y seleccione **propiedades**.  
  
5.  Expanda el **servicios** colección en la **propiedades** ventana para abrir la **Editor de colecciones ServiceReference** ventana.  
  
6.  Haga clic en **agregar**, especifique `CostService.svc` como el **ruta de acceso** hace referencia a y haga clic en **Aceptar**.  
  
7.  Expanda el **HTML** nodo en el **cuadro de herramientas** y arrastre y coloque una **entrada (botón)** en la página Default.aspx.  
  
8.  Haga clic en el **botón** y seleccione **propiedades**.  
  
9. Cambiar el **valor** campo `Price for 3 Sandwiches`.  
  
10. Haga doble clic en el **botón** para acceder al código de JavaScript.  
  
11. Pasar en el siguiente código de JavaScript en el <`script`> elemento.  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a>Obtener acceso al servicio desde el cliente  
  
1.  Utilice Ctrl + F5 para iniciar el servicio y el cliente web. Haga clic en el **precio de 3 bocadillos a la parrilla** botón para generar el resultado esperado de "3,75".  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo contiene el código del servicio contenido en el archivo WCFService.svc.cs y el código de cliente contenido en el archivo Default.aspx.  
  
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
