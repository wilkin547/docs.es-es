---
title: "Tipos conocidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d83720-ca38-4b2c-86a6-f149ed1d89ec
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Tipos conocidos
Este ejemplo muestra cómo especificar la información sobre los tipos derivados en un contrato de datos.Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios.En la programación orientada a objetos, un tipo que hereda de otro tipo se puede utilizar en lugar del tipo original.En la programación orientada a servicios, se comunican esquemas en lugar los tipos y por consiguiente, no se conserva la relación entre los tipos.El atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> permite información sobre los tipos derivados que deben incluirse en el contrato de datos.Si no se utiliza este mecanismo, un tipo derivado no se puede enviar o recibir donde se espera un tipo base.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El contrato de servicios para el servicio utiliza números complejos, como se muestra en el código muestra siguiente.  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
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
  
 <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> se aplican a la clase `ComplexNumber` para indicar qué campos de la clase se pueden pasar entre el cliente y el servicio.La clase derivada `ComplexNumberWithMagnitude` puede utilizarse en lugar de `ComplexNumber`.El atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> en el tipo `ComplexNumber` indica esto mismo.  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
[KnownType(typeof(ComplexNumberWithMagnitude))]  
public class ComplexNumber  
{  
    [DataMember]  
    public double Real = 0.0D;  
    [DataMember]  
    public double Imaginary = 0.0D;  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
  
```  
  
 El tipo `ComplexNumberWithMagnitude` deriva de `ComplexNumber` pero agrega un miembro de datos adicional, `Magnitude`.  
  
```  
  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class ComplexNumberWithMagnitude : ComplexNumber  
{  
    public ComplexNumberWithMagnitude(double real, double imaginary) :  
        base(real, imaginary) { }  
  
    [DataMember]  
    public double Magnitude  
    {  
        get { return Math.Sqrt(Imaginary*Imaginary  + Real*Real); }  
        set { throw new NotImplementedException(); }  
    }  
}  
```  
  
 Para mostrar la característica de tipos conocida, el servicio se implementa de tal manera que solo le devuelve `ComplexNumberWithMagnitude` para la suma y resta.\(Aunque el contrato especifica `ComplexNumber`, esto se permite debido al atributo `KnownTypeAttribute`\).La multiplicación y división devuelven el tipo base `ComplexNumber` .  
  
```  
public class DataContractCalculatorService : IDataContractCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        //Return the derived type.  
        return new ComplexNumberWithMagnitude(n1.Real + n2.Real,  
                                      n1.Imaginary + n2.Imaginary);  
    }  
  
    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)  
    {  
        //Return the derived type.  
        return new ComplexNumberWithMagnitude(n1.Real - n2.Real,   
                                 n1.Imaginary - n2.Imaginary);  
    }  
  
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)  
    {  
        double real1 = n1.Real * n2.Real;  
        double imaginary1 = n1.Real * n2.Imaginary;  
        double imaginary2 = n2.Real * n1.Imaginary;  
        double real2 = n1.Imaginary * n2.Imaginary * -1;  
        //Return the base type.  
        return new ComplexNumber(real1 + real2, imaginary1 +   
                                                  imaginary2);  
    }  
  
    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)  
    {  
        ComplexNumber conjugate = new ComplexNumber(n2.Real,   
                                     -1*n2.Imaginary);  
        ComplexNumber numerator = Multiply(n1, conjugate);  
        ComplexNumber denominator = Multiply(n2, conjugate);  
        //Return the base type.  
        return new ComplexNumber(numerator.Real / denominator.Real,  
                                             numerator.Imaginary);  
    }  
}  
```  
  
 En el cliente, el contrato de servicios y el contrato de datos se definen en el archivo de código fuente generatedClient.cs, generado por [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde los metadatos del servicio.Dado que el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> se especifica en el contrato de datos del servicio, el cliente puede recibir `ComplexNumber` y las clases `ComplexNumberWithMagnitude` al utilizar el servicio.El cliente detecta si obtuvo `ComplexNumberWithMagnitude` y generó el resultado adecuado:  
  
```  
// Create a client  
DataContractCalculatorClient client =   
    new DataContractCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber(); value1.real = 1; value1.imaginary = 2;  
ComplexNumber value2 = new ComplexNumber(); value2.real = 3; value2.imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.real, value1.imaginary, value2.real, value2.imaginary,  
    result.real, result.imaginary);  
if (result is ComplexNumberWithMagnitude)  
{  
    Console.WriteLine("Magnitude: {0}",   
        ((ComplexNumberWithMagnitude)result).Magnitude);  
}  
else  
{  
    Console.WriteLine("No magnitude was sent from the service");  
}  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Observe que se imprime una magnitud para la suma y resta pero no para la multiplicación y división debido a la manera en que se implementó el servicio.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Magnitude: 7.21110255092798  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Magnitude: 2.82842712474619  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
No magnitude was sent from the service  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i  
No magnitude was sent from the service  
  
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
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Data\KnownTypes`  
  
## Vea también