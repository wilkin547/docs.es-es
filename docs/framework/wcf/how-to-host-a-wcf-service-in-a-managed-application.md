---
title: "Hospedaje de un servicio WCF en una aplicaci&#243;n administrada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# Hospedaje de un servicio WCF en una aplicaci&#243;n administrada
Para hospedar un servicio dentro de una aplicación administrada, incruste el código del servicio dentro del código de la aplicación administrada, defina un extremo para el servicio de manera imperativa mediante código, de manera declarativa mediante configuración o usando extremos predeterminados y, a continuación, cree una instancia de <xref:System.ServiceModel.ServiceHost>.  
  
 Para comenzar a recibir mensajes, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.Esto crea y abre el agente de escucha del servicio.Hospedar un servicio de esta manera se conoce a menudo como "autohospedaje", puesto que la aplicación administrada está haciendo el propio trabajo de hospedaje.Para cerrar el servicio, llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName> en <xref:System.ServiceModel.ServiceHost>.  
  
 Un servicio también se puede hospedar en un servicio de Windows administrado, en Internet Information Services \(IIS\) o en Servicio de activación de procesos de Windows \(WAS\).[!INCLUDE[crabout](../../../includes/crabout-md.md)] las opciones de hospedaje para un servicio, vea [Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
 Hospedar un servicio en una aplicación administrada es la opción más flexible porque es la que necesita una menor infraestructura para su implementación.[!INCLUDE[crabout](../../../includes/crabout-md.md)] los servicios de hospedaje en aplicaciones administradas, vea [Hospedaje en una aplicación administrada](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
 El siguiente procedimiento muestra cómo implementar un servicio autohospedado en una aplicación de consola.  
  
### Creación de un servicio autohospedado  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **Nuevo**, **Proyecto** en el menú **Archivo**.  
  
2.  En la lista **Plantillas instaladas**, seleccione **Visual C\#**, **Windows** o **Visual Basic**, **Windows**.Dependiendo de la configuración de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], uno o ambas de estas opciones pueden estar debajo del nodo **Otros lenguajes** de la lista **Plantillas instaladas**.  
  
3.  Seleccione **Aplicación de consola** en la lista **Windows**.Escriba `SelfHost` en el cuadro **Nombre** y haga clic en **Aceptar**.  
  
4.  Haga clic con el botón secundario en **SelfHost** en el **Explorador de soluciones** y seleccione **Agregar referencia**.Seleccione **System.ServiceModel** en la pestaña **.NET** y haga clic en **Aceptar**.  
  
    > [!TIP]
    >  Si la ventana **Explorador de soluciones** no está visible, seleccione **Explorador de soluciones** en el menú **Ver**.  
  
5.  Haga doble clic en **Program.cs** o **Module1.vb** en el **Explorador de soluciones** para abrirlo en la ventana de código si aún no lo está.Agregue las instrucciones siguientes en la parte superior del archivo.  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  Defina e implemente un contrato de servicio.En este ejemplo se define un `HelloWorldService` que devuelve un mensaje en función de la entrada al servicio.  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo definir e implementar una interfaz de servicio, vea [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) y [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).  
  
7.  Al principio del método `Main`, cree una instancia de la clase <xref:System.Uri> con la dirección base del servicio.  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  Cree una instancia de la clase <xref:System.ServiceModel.ServiceHost>, pasando un <xref:System.Type> que representa el tipo de servicio y el Identificador uniforme de recursos \(URI\) de la dirección base al [ServiceHost\(Type, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.Habilite la publicación de metadatos y, a continuación, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost> para inicializar el servicio y prepararlo para recibir mensajes.  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]  
  
    > [!NOTE]
    >  En este ejemplo se usan extremos predeterminados, y este servicio no requiere ningún archivo de configuración.Si no se configura ningún extremo, el runtime crea uno para cada dirección base de cada contrato de servicio implementado por el servicio.[!INCLUDE[crabout](../../../includes/crabout-md.md)] los extremos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
### Para probar el servicio  
  
1.  Presione Ctrl \+ F5 para ejecutar el servicio.  
  
2.  Abra el **Cliente de prueba WCF**.  
  
    > [!TIP]
    >  Para abrir el **Cliente de prueba WCF**, abra un símbolo del sistema de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y ejecute **WcfTestClient.exe**.  
  
3.  Seleccione **Agregar servicio...** en el menú **Archivo**.  
  
4.  Escriba `http://localhost:8080/hello` en el cuadro de dirección y haga clic en **Aceptar**.  
  
    > [!TIP]
    >  Asegúrese de que el servicio se está ejecutando; de lo contrario, este paso producirá un error.Si ha cambiado la dirección base en el código, use dicha dirección en este paso.  
  
5.  Haga doble clic en **SayHello** debajo del nodo **Mis proyectos de servicios**.Escriba su nombre en la columna **Valor** de la lista **Solicitud** y haga clic en **Invocar**.Aparecerá un mensaje de respuesta en la lista **Respuesta**.  
  
## Ejemplo  
 El siguiente ejemplo crea un objeto <xref:System.ServiceModel.ServiceHost> para hospedar un servicio de tipo `HelloWorldService`, y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.Se proporciona una dirección base mediante código, se habilita la publicación de metadatos y se usan extremos predeterminados.  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## Vea también  
 <xref:System.Uri>   
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>   
 <xref:System.Configuration.ConfigurationManager>   
 [Procedimiento para hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)   
 [Autohospedaje](../../../docs/framework/wcf/samples/self-host.md)   
 [Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md)   
 [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)   
 [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md)