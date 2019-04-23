---
title: Procedimiento para recuperar metadatos e implementar un servicio conforme
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: edf8fe2f174202d19b075ec218f059ea9b988843
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322672"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Procedimiento para recuperar metadatos e implementar un servicio conforme
A menudo, no es el mismo rol quien diseña e implementa los servicios. En entornos donde las aplicaciones que interoperan son importantes, los contratos pueden diseñarse o describirse en lenguaje de descripción de servicios Web (WSDL), y un desarrollador deberá implementar un servicio compatible con el contrato proporcionado. También puede migrar un servicio existente a Windows Communication Foundation (WCF), pero conservar el formato. Además, los contratos dúplex exigen a los autores de llamadas que también implementen un contrato de devolución de llamada.  
  
 En estos casos, debe usar el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (o una herramienta equivalente) para generar una interfaz de contrato de servicio en un lenguaje administrado que puede implementar para cumplir los requisitos de la contrato. Normalmente el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) se usa para adquirir un contrato de servicio que se usa con un generador de canales o un tipo de cliente WCF, así como con un archivo de configuración de cliente que configura el enlace correcto y la dirección. Para utilizar el archivo de configuración generado, debe cambiarlo a un archivo de configuración de servicio. También puede ser necesario modificar el contrato de servicios.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Recuperar datos e implementar un servicio conforme  
  
1. Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) frente a los archivos de metadatos o un extremo de metadatos para generar un archivo de código.  
  
2. Busque la parte del archivo de código de salida que contiene la interfaz de interés (en caso de que haya más de una) y que se marca con el atributo <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. El ejemplo de código siguiente muestra las dos interfaces generadas por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La primera (`ISampleService`) es la interfaz del contrato de servicio que se implementa para crear un servicio conforme. La segunda (`ISampleServiceChannel`) es una interfaz del asistente, para uso del cliente, que extiende tanto la interfaz del contrato de servicio como <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, y que se utiliza en una aplicación cliente.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Si el WSDL no especifica una acción de respuesta para todas las operaciones, los contratos de operación generados pueden tener la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> establecida en el carácter comodín (*). Quite este valor de propiedades. De lo contrario, al implementar los metadatos del contrato de servicios, éstos no pueden exportarse para esas operaciones.  
  
4. Implemente la interfaz en una clase y hospede el servicio. Como ejemplo, vea [Cómo: Implementar un contrato de servicio](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), o vea una implementación simple, a continuación, en la sección ejemplo.  
  
5. En la configuración del cliente de los archivos que el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) genera, cambiar el [ \<cliente >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) sección de configuración para un [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección de configuración. (Para obtener un ejemplo de un archivo de configuración de la aplicación generado por un cliente, vea la siguiente sección "Ejemplo").  
  
6. Dentro de la [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuración, debe crearse un `name` atributo en el [ \<servicios >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección de configuración para el servicio implementación de.  
  
7. Establezca el atributo `name` del servicio en el nombre de configuración para la implementación del servicio.  
  
8. Agregue los elementos de configuración del punto de conexión que utilizan el contrato de servicios implementado a la sección de configuración de servicio.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra la mayor parte de un archivo de código generado mediante la ejecución de la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) frente a los archivos de metadatos.  
  
 El código siguiente muestra:  
  
-   La interfaz del contrato de servicio que, una vez implementada, es conforme a los requisitos de contrato (`ISampleService`).  
  
-   La interfaz del asistente para uso del cliente que extiende tanto la interfaz de contrato del servicio como <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, y que se utiliza en una aplicación cliente (`ISampleServiceChannel`).  
  
-   La clase del asistente que extiende <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>, y que se utiliza en una aplicación cliente (`SampleServiceClient`).  
  
-   El archivo de configuración generado desde el servicio.  
  
-   Una implementación de servicio `ISampleService` simple.  
  
-   Una conversión del archivo de configuración del cliente en una versión del servicio.  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]     

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]    

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]    
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
