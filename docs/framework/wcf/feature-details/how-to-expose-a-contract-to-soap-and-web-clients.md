---
title: Cómo exponer un contrato a clientes web y de SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: d82c5e3fc33528eadc3c404cca59a3dcf905e0e2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396960"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a>Cómo exponer un contrato a clientes web y de SOAP

De forma predeterminada, Windows Communication Foundation (WCF) hace que los puntos de conexión que estén disponibles sólo para clientes SOAP. En [Cómo: crear un servicio de WCF Web HTTP básico](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), un punto de conexión está disponible para los clientes que no sea SOAP. Puede haber veces en las que desee poner el mismo contrato a disposición de ambos modos, como, por ejemplo, un punto de conexión web y un punto de conexión SOAP. En este tema se muestra un ejemplo sobre cómo hacerlo.

## <a name="to-define-the-service-contract"></a>Para definir el contrato de servicio

1. Defina un contrato de servicio mediante una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> y <xref:System.ServiceModel.Web.WebGetAttribute> atributos, como se muestra en el código siguiente:

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > De forma predeterminada, <xref:System.ServiceModel.Web.WebInvokeAttribute> asigna las llamadas POST a la operación. Sin embargo, puede especificar el método para asignar a la operación especificando un parámetro “method=”. <xref:System.ServiceModel.Web.WebGetAttribute> no tiene un parámetro “method=” y solo asigna llamadas GET a la operación de servicio.

2. Implemente el contrato de servicio, tal como se muestra en el código siguiente:

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a>Para hospedar el servicio

1. Crear un <xref:System.ServiceModel.ServiceHost> de objeto, como se muestra en el código siguiente:

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. Agregar un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.BasicHttpBinding> para el extremo SOAP, tal como se muestra en el código siguiente:

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. Agregar un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.WebHttpBinding> para el punto de conexión no SOAP y agregue el <xref:System.ServiceModel.Description.WebHttpBehavior> al punto de conexión, como se muestra en el código siguiente:

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. Llame a `Open()` en un <xref:System.ServiceModel.ServiceHost> instancia para abrir el host del servicio, tal como se muestra en el código siguiente:

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a>Para llamar a las operaciones de servicio asignadas a GET en Internet Explorer

1. Abra Internet Explorer y escriba "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" y presione ENTRAR. La dirección URL contiene la dirección base del servicio (`http://localhost:8000/`), la dirección relativa del punto de conexión (""), la operación de servicio para llamar ("EchoWithGet") y un signo de interrogación seguido de una lista de parámetros con nombre separados por una y comercial (&).

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a>Realización de llamadas a las operaciones de servicio en el punto de conexión web mediante código

1. Cree una instancia de <xref:System.ServiceModel.Web.WebChannelFactory%601> dentro de un bloque `using`, tal y como se muestra en el código siguiente.

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> Se llama al método `Close()` de manera automática en el canal al final del bloque `using`.

1. Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a>Realización de llamadas a operaciones de servicio en el extremo SOAP

1. Cree una instancia de <xref:System.ServiceModel.ChannelFactory> dentro de un bloque `using`, tal y como se muestra en el código siguiente.

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a>Cierre del host de servicio

1. Cierre el host de servicio, tal y como se muestra en el código siguiente.

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a>Ejemplo

Este es el listado de este tema de código completo:

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a>Compilación del código

 Cuando se compila Service.cs, haga una referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)