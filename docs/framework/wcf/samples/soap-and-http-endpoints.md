---
title: puntos de conexión SOAP y HTTP
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: bf11563b937426c3c1701e7fed79e82e4e4669ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="soap-and-http-endpoints"></a>puntos de conexión SOAP y HTTP
Este ejemplo muestra cómo implementar un servicio basado en RPC y exponerlo en el formato SOAP y dar formato a la "Plain Old XML" (POX) mediante el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modelo de programación Web. Consulte la [servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) ejemplo para obtener más información sobre el enlace HTTP para el servicio. Este ejemplo se centra en los detalles relativos a la exposición del mismo servicio a través de SOAP y HTTP utilizando enlaces diferentes.  
  
## <a name="demonstrates"></a>Demostraciones  
 Exponer un servicio RPC sobre SOAP y HTTP utilizando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="discussion"></a>Explicación  
 Este ejemplo tiene dos componentes: un proyecto Aplicación web (Servicio) que contiene un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y una aplicación de consola (Cliente) que invoca las operaciones de servicio mediante enlaces HTTP y SOAP.  
  
 El servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expone dos operaciones, `GetData` y `PutData`, que repiten la cadena que se pasó como entrada. A las operaciones de servicio se les agregan los objetos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>. Estos atributos controlan la proyección HTTP de estas operaciones. Además, se les agrega el objeto <xref:System.ServiceModel.OperationContractAttribute>, que les permite ser expuestos a través de enlaces SOAP. El método `PutData` del servicio inicia una excepción <xref:System.ServiceModel.Web.WebFaultException>, que se devuelve a través de HTTP utilizando el código de estado HTTP y se devuelve a través de SOAP como un error de SOAP.  
  
 El archivo Web.config configura el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con tres extremos:  
  
-   El extremo ~/service.svc/mex que expone los metadatos del servicio para el acceso de los clientes basados en SOAP.  
  
-   El extremo ~/service.svc/http que permite a los clientes tener acceso al servicio utilizando el enlace HTTP.  
  
-   El extremo ~/service.svc/soap que permite a los clientes tener acceso al servicio utilizando el enlace SOAP sobre HTTP.  
  
 El extremo HTTP se configura con un extremo estándar <`webHttp`> que tiene `helpEnabled` establecido en `true`. Como resultado, el servicio expone XHTML basado en la página de Ayuda en ~/service.svc/http/help que los clientes basados en HTTP pueden utilizar para tener acceso al servicio.  
  
 El proyecto cliente muestra cómo tener acceso al servicio utilizando un proxy SOAP (generado a través de **Agregar referencia de servicio**) y obtener acceso a la de servicio mediante <xref:System.Net.WebClient>.  
  
 El ejemplo está compuesto de un servicio hospedado en web y una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución para obtener el ejemplo de extremos HTTP y SOAP.  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Si no está abierto, presione CTRL+W, S para abrir el **el Explorador de soluciones** ventana.  
  
4.  Desde el **el Explorador de soluciones** ventana, haga clic en el **servicio** proyecto y coloque el cursor sobre la **depurar** opción del menú contextual para que la **Iniciar nueva Instancia** aparece el menú contextual. Haga clic en **Iniciar nueva instancia**. De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5.  Desde las ventanas del explorador de soluciones, haga clic en el proyecto de cliente y coloque el cursor sobre la **depurar** opción del menú contextual para que la **Iniciar nueva instancia** aparece el menú contextual. Haga clic en **Iniciar nueva instancia**.  
  
6.  La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.  
  
7.  A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
8.  Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
9. Presione MAYÚS+F5 para dejar de depurar el servicio.  
  
10. En el área de notificación de Windows, haga clic en el icono del servidor de desarrollo de ASP.NET y seleccione **detener** en el menú contextual.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
