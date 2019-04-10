---
title: Compatibilidad con POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: 86ade3a6b045f6f7c57e4a95936b4f1574b51ff0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334905"
---
# <a name="poco-support"></a>Compatibilidad con POCO
En este ejemplo se muestra la compatibilidad para la serialización de los tipos sin marca; es decir, tipos a los que no se han aplicado atributos de serialización, a veces conocidos como tipos de objetos CLR antiguos sin formato (POCO). <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos para todos los tipos públicos sin marca que tienen un constructor predeterminado. Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios. Para obtener más información acerca de los tipos no marcados, vea [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), pero utiliza números complejos en lugar de los tipos numéricos primitivos. También es similar a la [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) de ejemplo, salvo que el <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> no se utilizan los atributos.  
  
 El cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La clase `ComplexNumber` se utiliza en la clase `ServiceContract`. El tipo `ComplexNumber` no tiene los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>, como se muestra en el siguiente código de ejemplo. De manera predeterminada, se serializan todas las propiedades y campos públicos.  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md)
