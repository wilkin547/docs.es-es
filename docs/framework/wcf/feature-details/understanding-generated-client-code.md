---
description: 'Más información acerca de: Descripción del código de cliente generado'
title: Comprender códigos de cliente generado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3f6e4b0-1131-4c94-aa39-a197c5c2f2ca
ms.openlocfilehash: c95f02a257cd9417b94190c82fe426a1550f1bf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732961"
---
# <a name="understanding-generated-client-code"></a>Comprender códigos de cliente generado

[ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) genera código de cliente y un archivo de configuración de la aplicación cliente para su uso en la compilación de aplicaciones cliente. Este tema proporciona un recorrido por los ejemplos de código generados para los escenarios de contrato de servicio estándar. Para obtener más información sobre cómo compilar una aplicación cliente mediante el código generado, consulte [información general del cliente de WCF](../wcf-client-overview.md).  
  
## <a name="overview"></a>Información general  

 Si usa Visual Studio para generar tipos de cliente Windows Communication Foundation (WCF) para su proyecto, normalmente no es necesario examinar el código de cliente generado. Si no usa un entorno de desarrollo que realice los mismos servicios automáticamente, puede usar una herramienta como Svcutil.exe para generar el código de cliente y, a continuación, usar ese código para desarrollar la aplicación cliente.  
  
 Dado que Svcutil.exe tiene varias opciones que modifican la información de tipo generada, este tema no discute todos los escenarios. Sin embargo, las tareas estándar siguientes implican la ubicación del código generado:  
  
- Identificar las interfaces del contrato de servicio.  
  
- Identificar la clase de cliente WCF.  
  
- Identificar los tipos de datos.  
  
- Identificar los contratos de devolución de llamada para los servicios dúplex.  
  
- Identificar la interfaz de canal de contrato de servicio del asistente.  
  
### <a name="finding-service-contract-interfaces"></a>Buscar las interfaces del contrato de servicio  

 Buscar las interfaces que modelan los servicios modelo, buscar las interfaces marcadas con el atributo <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> . A menudo este atributo puede ser difícil de buscar con una lectura rápida debido a la presencia de otros atributos y las propiedades explícitas establecidas en el propio atributo. Recuerde que la interfaz del contrato de servicio y la interfaz del contrato del cliente son dos tipos diferentes. El ejemplo de código siguiente muestra el contrato de servicios original.  
  
 [!code-csharp[C_GeneratedCodeFiles#22](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#22)]  
  
 El ejemplo de código siguiente muestra el mismo contrato de servicios tal y como lo genera Svcutil.exe.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Puede utilizar la interfaz de contrato de servicio generada junto con la <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> clase para crear un objeto de canal de WCF con el que invocar las operaciones de servicio. Para obtener más información, vea [Cómo: usar ChannelFactory](how-to-use-the-channelfactory.md).  
  
### <a name="finding-wcf-client-classes"></a>Buscar las clases de cliente de WCF  

 Para buscar la clase de cliente de WCF que implementa el contrato de servicio que desea utilizar, busque una extensión de <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> , donde el parámetro de tipo es la interfaz de contrato de servicio que encontró anteriormente y que extiende esa interfaz. En el ejemplo de código siguiente se muestra la clase <xref:System.ServiceModel.ClientBase%601> de tipo `ISampleService`.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Puede usar esta clase de cliente WCF creando una nueva instancia de ella y llamando a los métodos que implementa. Esos métodos invocan la operación del servicio con la que está diseñado y está configurado para interactuar. Para obtener más información, consulte [información general del cliente de WCF](../wcf-client-overview.md).  
  
> [!NOTE]
> Cuando SvcUtil.exe genera una clase de cliente WCF, agrega <xref:System.Diagnostics.DebuggerStepThroughAttribute> a la clase de cliente para evitar que los depuradores recorran la clase de cliente WCF.  
  
### <a name="finding-data-types"></a>Buscar los tipos de datos  

 Para encontrar los tipos de datos en el código generado, el mecanismo más básico es identificar el nombre del tipo especificado en un contrato y buscar el código para esa declaración de tipos. Por ejemplo, el contrato siguiente especifica que `SampleMethod` puede devolver un error de SOAP de tipo `microsoft.wcf.documentation.SampleFault`.  
  
 [!code-csharp[C_GeneratedCodeFiles#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#11)]  
  
 Al buscar `SampleFault` , se busca la declaración de tipos siguiente.  
  
 [!code-csharp[C_GeneratedCodeFiles#30](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#30)]  
  
 En este caso, el tipo de datos es el tipo de datos iniciado por una excepción específica en el cliente, <xref:System.ServiceModel.FaultException%601> donde el parámetro de tipo de datos es `microsoft.wcf.documentation.SampleFault`. Para obtener más información sobre los tipos de datos, vea [especificar transferencia de datos en contratos de servicio](specifying-data-transfer-in-service-contracts.md). Para obtener más información sobre el control de excepciones en los clientes, consulte [envío y recepción de errores](../sending-and-receiving-faults.md).  
  
### <a name="finding-callback-contracts-for-duplex-services"></a>Buscar los contratos de devolución de llamada para los servicios dúplex  

 Si busca un contrato de servicios para el cual la interfaz de contrato especifica un valor para la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> , a continuación, ese contrato especifica un contrato dúplex. Los contratos dúplex exigen a la aplicación cliente que cree una clase de devolución de llamada que implemente el contrato de devolución de llamada y pase una instancia de esa clase a <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType> o <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType> usando para comunicarse con el servicio. Para obtener más información acerca de los clientes dúplex, consulte [Cómo: obtener acceso a los servicios con un contrato dúplex](how-to-access-services-with-a-duplex-contract.md).  
  
 El contrato siguiente especifica un contrato de devolución de llamada de tipo `SampleDuplexHelloCallback`.  
  
 [!code-csharp[C_GeneratedCodeFiles#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#2)]
 [!code-vb[C_GeneratedCodeFiles#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#2)]  
  
 Buscar ese contrato de devolución de llamada busca la interfaz siguiente que la aplicación cliente debe implementar.  
  
 [!code-csharp[C_GeneratedCodeFiles#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#4)]
 [!code-vb[C_GeneratedCodeFiles#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#4)]  
  
### <a name="finding-service-contract-channel-interfaces"></a>Buscar interfaces de canal de contrato de servicios  

 Al utilizar la clase <xref:System.ServiceModel.ChannelFactory> con una interfaz del contrato de servicios, debe convertirse a la interfaz <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> para abrir, cerrar, o anular el canal explícitamente. Para facilitar su funcionamiento, la herramienta Svcutil.exe también genera una interfaz del asistente que implementa la interfaz del contrato de servicio y <xref:System.ServiceModel.IClientChannel> para permitir que usted interactúe con la infraestructura del canal de cliente sin tener que convertirse. El código siguiente muestra la definición de un canal de cliente del asistente que implementa el contrato de servicios anterior.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a un cliente WCF](../wcf-client-overview.md)
