---
title: Extremos SOAP y HTTP
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: f10b1aa4514aee50c0c0d17cabdb9516a3ca7584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144024"
---
# <a name="soap-and-http-endpoints"></a>Extremos SOAP y HTTP
En este ejemplo se muestra cómo implementar un servicio basado en RPC y exponerlo en el formato SOAP y el formato "Plain Old XML" (POX) mediante el modelo de programación Web WCF. Consulte el ejemplo [de servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) para obtener más detalles sobre el enlace HTTP para el servicio. Este ejemplo se centra en los detalles relativos a la exposición del mismo servicio a través de SOAP y HTTP utilizando enlaces diferentes.  
  
## <a name="demonstrates"></a>Muestra  
 Exponer un servicio RPC a través de SOAP y HTTP mediante WCF.  
  
## <a name="discussion"></a>Discusión  
 Este ejemplo consta de dos componentes: un proyecto de aplicación web (servicio) que contiene un servicio WCF y una aplicación de consola (cliente) que invoca operaciones de servicio mediante enlaces SOAP y HTTP.  
  
 El servicio WCF expone`GetData` 2 `PutData` operaciones y que se hacen eco de la cadena que se pasó como entrada. A las operaciones de servicio se les anotan los objetos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>. Estos atributos controlan la proyección HTTP de estas operaciones. Además, se les anota el objeto <xref:System.ServiceModel.OperationContractAttribute>, que les permite ser expuestos a través de enlaces SOAP. El método `PutData` del servicio inicia una excepción <xref:System.ServiceModel.Web.WebFaultException>, que se devuelve a través de HTTP utilizando el código de estado HTTP y se devuelve a través de SOAP como un error de SOAP.  
  
 El archivo Web.config configura el servicio WCF con 3 extremos:  
  
- El punto de conexión ~/service.svc/mex que expone los metadatos del servicio para el acceso de los clientes basados en SOAP.  
  
- El punto de conexión ~/service.svc/http que permite a los clientes tener acceso al servicio utilizando el enlace HTTP.  
  
- El punto de conexión ~/service.svc/soap que permite a los clientes tener acceso al servicio utilizando el enlace SOAP sobre HTTP.  
  
 El punto de conexión `webHttp` HTTP se configura `helpEnabled` con `true`un <> punto de conexión estándar que se ha establecido en . Como resultado, el servicio expone XHTML basado en la página de Ayuda en ~/service.svc/http/help que los clientes basados en HTTP pueden utilizar para tener acceso al servicio.  
  
 El proyecto de cliente muestra el acceso al servicio mediante un proxy SOAP <xref:System.Net.WebClient>(generado a través de Agregar referencia de **servicio**) y el acceso al servicio mediante .  
  
 El ejemplo está compuesto de un servicio hospedado en web y una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1. Abra la solución para obtener el ejemplo de extremos HTTP y SOAP.  
  
2. Presione CTRL+MAYÚS+B para compilar la solución.  
  
3. Si aún no está abierto, presione CTRL+W, S para abrir la ventana **Explorador** de soluciones.  
  
4. En la ventana **Explorador** de soluciones, haga clic con el botón secundario en el proyecto **de** servicio y coloque el cursor sobre la opción de menú contextual **Depurar** para que aparezca el menú contextual Iniciar **nueva instancia.** Haga clic en **Iniciar nueva instancia**. De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5. En las ventanas del Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y coloque el cursor sobre la opción de menú contextual **Depurar** para que aparezca el menú contextual **Iniciar nueva instancia.** Haga clic en **Iniciar nueva instancia**.  
  
6. La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.  
  
7. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
8. Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
9. Presione MAYÚS+F5 para dejar de depurar el servicio.  
  
10. En el área de notificación de Windows, haga clic con el botón derecho en el icono del servidor de desarrollo de ASP.NET y seleccione **Detener** en el menú contextual.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
