---
title: "C&#243;mo recuperar los metadatos e implementar un servicio conforme | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo recuperar los metadatos e implementar un servicio conforme
A menudo, no es el mismo rol quien diseña e implementa los servicios. En entornos donde las aplicaciones que interoperan son importantes, los contratos pueden diseñarse o describirse en lenguaje de descripción de servicios Web (WSDL), y un desarrollador deberá implementar un servicio compatible con el contrato proporcionado. También puede desear migrar un servicio existente a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] pero conservar el formato de conexión. Además, los contratos dúplex exigen a los autores de llamadas que también implementen un contrato de devolución de llamada.  
  
 En estos casos, debe utilizar el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (o una herramienta equivalente) para generar una interfaz de contrato de servicio en un lenguaje administrado que puede implementar para cumplir los requisitos del contrato. Normalmente la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) se usa para adquirir un contrato de servicio que se usa con un generador de canales o un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , así como con un archivo de configuración de cliente configura el enlace correcto y la dirección de tipo de cliente. Para utilizar el archivo de configuración generado, debe cambiarlo a un archivo de configuración de servicio. También puede ser necesario modificar el contrato de servicios.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Recuperar datos e implementar un servicio conforme  
  
1.  Utilice la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) contra un extremo de metadatos para generar un archivo de código o archivos de metadatos.  
  
2.  Busque la parte del código del archivo de salida que contiene la interfaz de interés (en el caso que hay más de uno) que se marca con el <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> atributo. En el ejemplo de código siguiente se muestra las dos interfaces generadas por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La primera (`ISampleService`) es la interfaz del contrato de servicio que se implementa para crear un servicio conforme. El segundo (`ISampleServiceChannel`) es una interfaz auxiliar para uso del cliente que extiende la interfaz de contrato de servicio y <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> es para uso en una aplicación cliente.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  Si el archivo WSDL no especifica una acción de respuesta para todas las operaciones, los contratos de operación generados pueden tener la <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> propiedad establecida en el carácter comodín (*). Quite este valor de propiedades. De lo contrario, al implementar los metadatos del contrato de servicios, éstos no pueden exportarse para esas operaciones.  
  
4.  Implemente la interfaz en una clase y hospede el servicio. Para obtener un ejemplo, vea [Cómo: implementar un contrato de servicio](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), o vea una implementación simple, a continuación, en la sección ejemplo.  
  
5.  En la configuración del cliente de los archivos que el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) genera, cambiar la [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) sección de configuración a una [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección de configuración. (Para obtener un ejemplo de un archivo de configuración de la aplicación generado por un cliente, vea la siguiente sección "Ejemplo").  
  
6.  Dentro de la [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configuración, debe crearse un `name` el atributo en el [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección de configuración para la implementación del servicio.  
  
7.  Establezca el atributo `name` del servicio en el nombre de configuración para la implementación del servicio.  
  
8.  Agregue los elementos de configuración del punto de conexión que utilizan el contrato de servicios implementado a la sección de configuración de servicio.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra la mayor parte de un archivo de código generado mediante la ejecución de la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con los archivos de metadatos.  
  
 El código siguiente muestra:  
  
-   La interfaz del contrato de servicio que, una vez implementada, es conforme a los requisitos de contrato (`ISampleService`).  
  
-   La interfaz auxiliar para uso del cliente que extiende la interfaz de contrato de servicio y <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> y que se utiliza en una aplicación de cliente (`ISampleServiceChannel`).  
  
-   La clase auxiliar que extiende <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> y que se utiliza en una aplicación de cliente (`SampleServiceClient`).  
  
-   El archivo de configuración generado desde el servicio.  
  
-   Una implementación de servicio `ISampleService` simple.  
  
-   Una conversión del archivo de configuración del cliente en una versión del servicio.  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#10](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/client.exe.config#10)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]  -->  
  
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#20](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/hostapplication.exe.config#20)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)