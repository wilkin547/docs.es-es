---
description: Más información acerca de cómo establecer las propiedades de uso y estilo
title: Establecer los ejemplos de propiedades de estilo y uso
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: 435ea23e4a34ec91ea764ae9435487c1e1313afd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793004"
---
# <a name="setting-the-use-and-style-properties"></a>Establecimiento del uso y estilo de las propiedades

En este ejemplo se muestra cómo se utiliza el uso y las propiedades de estilo en <xref:System.ServiceModel.XmlSerializerFormatAttribute> y en <xref:System.ServiceModel.DataContractFormatAttribute>. Estas propiedades afectan a la forma en que se ha dado formato a los mensajes. De forma predeterminada, se da formato al cuerpo del mensaje con el estilo establecido en <xref:System.ServiceModel.OperationFormatStyle.Document>. Esta configuración se puede especificar en el nivel del contrato de servicios o en el nivel del contrato de operación.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

La propiedad de estilo <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> determina cómo se da formato a los metadatos de WSDL para el servicio. Los valores posibles son <xref:System.ServiceModel.OperationFormatStyle.Document>, y <xref:System.ServiceModel.OperationFormatStyle.Rpc>. RPC significa que la representación de WSDL de los mensajes intercambiados para una operación contiene parámetros como si fuera una llamada de procedimiento remoto. A continuación se muestra un ejemplo.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

Establecer el estilo en <xref:System.ServiceModel.OperationFormatStyle.Document> quiere decir que la representación de WSDL contiene un elemento único que representa el documento que se intercambia para una operación tal y como se muestra en el ejemplo siguiente.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

La propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> determina el formato del mensaje. Los valores posibles son <xref:System.ServiceModel.OperationFormatUse.Literal> y <xref:System.ServiceModel.OperationFormatUse.Encoded>; el valor predeterminado es <xref:System.ServiceModel.OperationFormatUse.Literal>. Literal significa que el mensaje es una instancia literal del esquema en WSDL, tal y como se muestra en el siguiente ejemplo de documento/literal.

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

Codificado significa que los esquemas en WSDL son especificaciones abstractas que se codifican según las reglas situadas en la sección 5 de SOAP 1.1. El siguiente es un ejemplo de RPC/Encoded.

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

El WS-I Basic Profile 1.0 prohibe el uso de <xref:System.ServiceModel.OperationFormatUse.Encoded> y se debería utilizar solo cuando los servicios heredados así lo requieran. El formato de mensaje `Encoded` solo está disponible al utilizar XmlSerializer.

Para que pueda ver los mensajes que se envían y se reciben, este ejemplo se basa en el [seguimiento y el registro de mensajes](tracing-and-message-logging.md). La configuración de servicio y código fuente se han modificado para habilitar y utilizar el seguimiento y registro de mensajes. Además, <xref:System.ServiceModel.WSHttpBinding> se ha configurado sin la seguridad, por lo que los mensajes anotados se pueden ver en un formato no cifrado. Los registros de seguimiento resultantes (System. ServiceModel. E2E y Message. log) se deben ver mediante la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md). Los rastros se configuran para ser creados en la carpeta C:\LOGS. Cree la carpeta antes de ejecutar el ejemplo. Para ver el contenido del mensaje en la herramienta Visor de seguimiento, seleccione **mensajes** en los paneles izquierdo y derecho de la herramienta.

El código siguiente muestra el contrato de servicios con la propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> establecida en <xref:System.ServiceModel.OperationFormatUse> y el formato del cuerpo del mensaje cambiados del <xref:System.ServiceModel.OperationFormatStyle> predeterminado a <xref:System.ServiceModel.OperationFormatStyle.Document>.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),
XmlSerializerFormat(Style = OperationFormatStyle.Rpc,
                                 Use = OperationFormatUse.Encoded)]
public interface IUseAndStyleCalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

Para ver la diferencia entre el <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> diferente y los valores <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, modifíquelos en el servicio, regenere el cliente, ejecute el ejemplo y examine el archivo c:\logs\message.logs con la herramienta Service Trace Viewer. Observe también el impacto en los metadatos viendo `http://localhost/ServiceModelSamples/service.svc?wsdl` . Los metadatos para los servicios se irrumpen normalmente en varias páginas. La Página principal de WSDL contiene los enlaces de WSDL, pero la vista `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` para observar las definiciones de los mensajes.

## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Cree un directorio C:\LOGS para registrar los mensajes. Proporcione a los usuarios permisos de escritura de servicio de red para este directorio.

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
