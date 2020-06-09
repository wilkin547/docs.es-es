---
title: Compatibilidad con POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: a9f8d185c58b22e68f7a8c11954e0e534c4bd48f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600469"
---
# <a name="poco-support"></a>Compatibilidad con POCO
En este ejemplo se muestra la compatibilidad para la serialización de los tipos sin marca; es decir, tipos a los que no se han aplicado atributos de serialización, a veces conocidos como tipos de objetos CLR antiguos sin formato (POCO). <xref:System.Runtime.Serialization.DataContractSerializer>Deduce un contrato de datos para todos los tipos públicos no marcados que tienen un constructor sin parámetros. Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios. Para obtener más información sobre los tipos no marcados, vea [tipos serializables](../feature-details/serializable-types.md).  
  
 Este ejemplo se basa en el [Introducción](getting-started-sample.md), pero utiliza números complejos en lugar de tipos numéricos primitivos. También es similar al ejemplo de [contrato de datos básico](basic-data-contract.md) , con la excepción de que <xref:System.Runtime.Serialization.DataContractAttribute> <xref:System.Runtime.Serialization.DataMemberAttribute> no se utilizan los atributos y.  
  
 El cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
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
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Tipos serializables](../feature-details/serializable-types.md)
