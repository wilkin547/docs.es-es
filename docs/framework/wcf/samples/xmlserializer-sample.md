---
title: "Ejemplo de XMLSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Ejemplo de XMLSerializer
Este ejemplo muestra cómo serializar y deserializar tipos que sean compatibles con <xref:System.Xml.Serialization.XmlSerializer>.El formateador de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] predeterminado es la clase <xref:System.Runtime.Serialization.DataContractSerializer>.Se puede usar la clase <xref:System.Xml.Serialization.XmlSerializer> para serializar y deserializar los tipos cuando no se puede utilizar la clase <xref:System.Runtime.Serialization.DataContractSerializer>.Éste es a menudo el caso cuando se requiere el control preciso sobre XML; por ejemplo, si un dato debe ser un atributo XML y no un elemento XML.Además, <xref:System.Xml.Serialization.XmlSerializer> se selecciona automáticamente cuando se crean clientes para servicios que no sean de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 En este ejemplo, el cliente es una aplicación de consola \(.exe\) e Internet Information Services \(IIS\) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.XmlSerializerFormatAttribute> se deben aplicar a la interfaz tal y como se muestra en el código de muestra siguiente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
  
```  
  
 <xref:System.Xml.Serialization.XmlSerializer> serializa los miembros públicos de la clase `ComplexNumber` como atributos XML.<xref:System.Runtime.Serialization.DataContractSerializer> no se puede utilizar para crear este tipo de instancia XML.  
  
```  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 La implementación del servicio calcula y devuelve los resultados adecuados, aceptando y devolviendo valores del tipo `ComplexNumber`.  
  
```  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
  
```  
  
 La implementación del cliente también utiliza números complejos.El contrato de servicios y los tipos de datos se definen en el archivo de código fuente generatedClient.cs, que fue generado por [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde los metadatos del servicio.Svcutil.exe puede detectar cuándo no es serializable un contrato por <xref:System.Runtime.Serialization.DataContractSerializer> y vuelve a tipos de `XmlSerializable` emisores en este caso.Si desea forzar el uso de <xref:System.Xml.Serialization.XmlSerializer>, puede pasar la opción de comando \/serializer:XmlSerializer \(utilice XmlSerializer\) a la herramienta Svcutil.exe.  
  
```  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione Entrar en la ventana de cliente para cerrar el cliente.  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## Vea también