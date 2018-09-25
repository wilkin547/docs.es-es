---
title: Hospedaje de un servicio WCF en una aplicación administrada
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113681"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Cómo: hospedar un servicio WCF en una aplicación administrada

Para hospedar un servicio dentro de una aplicación administrada, incruste el código del servicio dentro del código de la aplicación administrada, defina un extremo para el servicio de manera imperativa mediante código, de manera declarativa mediante configuración o usando extremos predeterminados y, a continuación, cree una instancia de <xref:System.ServiceModel.ServiceHost>.

Para comenzar a recibir mensajes, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>. Esto crea y abre el agente de escucha del servicio. Hospedar un servicio de esta manera se conoce a menudo como "autohospedaje", puesto que la aplicación administrada está haciendo el propio trabajo de hospedaje. Para cerrar el servicio, llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost>.

Un servicio también se puede hospedar en un servicio de Windows administrado, en Internet Information Services (IIS) o en Servicio de activación de procesos de Windows (WAS). Para obtener más información acerca de las opciones para un servicio de hospedaje, vea [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).

Hospedar un servicio en una aplicación administrada es la opción más flexible porque es la que necesita una menor infraestructura para su implementación. Para obtener más información sobre el hospedaje de servicios en las aplicaciones administradas, vea [hospedaje en una aplicación administrada](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).

El siguiente procedimiento muestra cómo implementar un servicio autohospedado en una aplicación de consola.

## <a name="create-a-self-hosted-service"></a>Crear un servicio autohospedado

1. Cree una nueva aplicación de consola:

   1. Abra Visual Studio y seleccione **New** > **proyecto** desde el **archivo** menú.

   2. En el **plantillas instaladas** lista, seleccione **Visual C#** o **Visual Basic**y, a continuación, seleccione **Windows Desktop**.

   3. Seleccione el **aplicación de consola** plantilla. Tipo `SelfHost` en el **nombre** cuadro y, a continuación, elija **Aceptar**.

2. Haga clic en **SelfHost** en **el Explorador de soluciones** y seleccione **Agregar referencia**. Seleccione **System.ServiceModel** desde el **.NET** ficha y, a continuación, elija **Aceptar**.

    > [!TIP]
    > Si el **el Explorador de soluciones** ventana no está visible, seleccione **el Explorador de soluciones** desde el **vista** menú.

3. Haga doble clic en **Program.cs** o **Module1.vb** en **el Explorador de soluciones** para abrirlo en la ventana de código, si aún no está abierto. Agregue las siguientes instrucciones en la parte superior del archivo:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Defina e implemente un contrato de servicio. En este ejemplo se define un `HelloWorldService` que devuelve un mensaje en función de la entrada al servicio.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Para obtener más información acerca de cómo definir e implementar una interfaz de servicio, consulte [Cómo: definir un contrato de servicio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) y [Cómo: implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).

5. Al principio del método `Main`, cree una instancia de la clase <xref:System.Uri> con la dirección base del servicio.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Cree una instancia de la clase <xref:System.ServiceModel.ServiceHost>, pasando un <xref:System.Type> que representa el tipo de servicio y el Identificador uniforme de recursos (URI) de la dirección base al <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>. Habilite la publicación de metadatos y, a continuación, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost> para inicializar el servicio y prepararlo para recibir mensajes.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > En este ejemplo se usan puntos de conexión predeterminados, y este servicio no requiere ningún archivo de configuración. Si no se configura ningún punto de conexión, el tiempo de ejecución crea uno para cada dirección base de cada contrato de servicio implementado por el servicio. Para obtener más información sobre los puntos de conexión predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

7. Presione **Ctrl**+**MAYÚS**+**B** para compilar la solución.

## <a name="test-the-service"></a>Probar el servicio

1. Presione **Ctrl**+**F5** para ejecutar el servicio.

2. Abra **cliente de prueba WCF**.

    > [!TIP]
    > Para abrir **cliente de prueba WCF**, abra el símbolo del sistema para desarrolladores para Visual Studio y ejecute **WcfTestClient.exe**.

3. Seleccione **Agregar servicio** desde el **archivo** menú.

4. Tipo `http://localhost:8080/hello` en el cuadro de dirección y haga clic en **Aceptar**.

    > [!TIP]
    > Asegúrese de que el servicio se está ejecutando; de lo contrario, este paso producirá un error. Si ha cambiado la dirección base en el código, use dicha dirección en este paso.

5. Haga doble clic en **SayHello** bajo el **Mis proyectos de servicios** nodo. Escriba su nombre en el **valor** columna en el **solicitar** lista y haga clic en **Invoke**.

   Aparece un mensaje de respuesta en el **respuesta** lista.

## <a name="example"></a>Ejemplo

El siguiente ejemplo crea un objeto <xref:System.ServiceModel.ServiceHost> para hospedar un servicio de tipo `HelloWorldService`, y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>. Se proporciona una dirección base mediante código, se habilita la publicación de metadatos y se usan puntos de conexión predeterminados.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>Vea también

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Cómo: hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
- [Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md)
- [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md)