---
title: Extremos SOAP y HTTP
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: 93f410b8b8632b0158d0a52b12845f1e8cec132c
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716682"
---
# <a name="soap-and-http-endpoints"></a>Extremos SOAP y HTTP
Este ejemplo muestra cómo implementar un servicio basado en RPC y exponerlo en el formato SOAP y en el formato POX (XML sin formato) mediante el modelo de programación web de WCF. Vea el ejemplo de [servicio http básico](../../../../docs/framework/wcf/samples/basic-http-service.md) para obtener más detalles sobre el enlace http para el servicio. Este ejemplo se centra en los detalles relativos a la exposición del mismo servicio a través de SOAP y HTTP utilizando enlaces diferentes.  
  
## <a name="demonstrates"></a>Demostraciones  
 Exponer un servicio RPC a través de SOAP y HTTP mediante WCF.  
  
## <a name="discussion"></a>Discusión  
 Este ejemplo consta de dos componentes: un proyecto de aplicación web (servicio) que contiene un servicio WCF y una aplicación de consola (cliente) que invoca operaciones de servicio mediante enlaces HTTP y SOAP.  
  
 El servicio WCF expone dos operaciones (`GetData` y `PutData`) que devuelven la cadena que se pasó como entrada. A las operaciones de servicio se les anotan los objetos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>. Estos atributos controlan la proyección HTTP de estas operaciones. Además, se les anota el objeto <xref:System.ServiceModel.OperationContractAttribute>, que les permite ser expuestos a través de enlaces SOAP. El método `PutData` del servicio inicia una excepción <xref:System.ServiceModel.Web.WebFaultException>, que se devuelve a través de HTTP utilizando el código de estado HTTP y se devuelve a través de SOAP como un error de SOAP.  
  
 El archivo Web. config configura el servicio WCF con 3 puntos de conexión:  
  
- El punto de conexión ~/service.svc/mex que expone los metadatos del servicio para el acceso de los clientes basados en SOAP.  
  
- El punto de conexión ~/service.svc/http que permite a los clientes tener acceso al servicio utilizando el enlace HTTP.  
  
- El punto de conexión ~/service.svc/soap que permite a los clientes tener acceso al servicio utilizando el enlace SOAP sobre HTTP.  
  
 El extremo HTTP se configura con un <`webHttp`> extremo estándar que tiene `helpEnabled` establecido en `true`. Como resultado, el servicio expone XHTML basado en la página de Ayuda en ~/service.svc/http/help que los clientes basados en HTTP pueden utilizar para tener acceso al servicio.  
  
 El proyecto de cliente muestra el acceso al servicio mediante un proxy SOAP (generado a través de **Agregar referencia de servicio**) y el acceso al servicio mediante <xref:System.Net.WebClient>.  
  
 El ejemplo está compuesto de un servicio hospedado en web y una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1. Abra la solución para obtener el ejemplo de extremos HTTP y SOAP.  
  
2. Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3. Si aún no está abierto, presione CTRL + W, S para abrir la ventana de **Explorador de soluciones** .  
  
4. En la ventana de **Explorador de soluciones** , haga clic con el botón secundario en el proyecto de **servicio** y coloque el cursor sobre la opción de menú contextual **depurar** para que aparezca el menú contextual **Iniciar nueva instancia** . Haga clic en **Iniciar nueva instancia**. De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5. En el Explorador de soluciones ventanas, haga clic con el botón secundario en el proyecto de cliente y coloque el cursor sobre la opción de menú contextual **depurar** para que aparezca el menú contextual **Iniciar nueva instancia** . Haga clic en **Iniciar nueva instancia**.  
  
6. La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.  
  
7. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
8. Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
9. Presione MAYÚS+F5 para dejar de depurar el servicio.  
  
10. En el área de notificación de Windows, haga clic con el botón secundario en el icono del servidor de desarrollo ASP.NET y seleccione **detener** en el menú contextual.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
