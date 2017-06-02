---
title: "Compatibilidad con POCO | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Compatibilidad con POCO
En este ejemplo se muestra la compatibilidad para la serialización de los tipos sin marca; es decir, tipos a los que no se han aplicado atributos de serialización, a veces conocidos como tipos de objetos CLR antiguos sin formato \(POCO\).<xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos para todos los tipos públicos sin marca que tienen un constructor predeterminado.Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los tipos no marcados, vea [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Este ejemplo está basado en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), pero utiliza los números complejos en lugar de los tipos numéricos primitivos.También es similar al ejemplo [Contrato de datos básico](../../../../docs/framework/wcf/samples/basic-data-contract.md), solo que no se utilizan los atributos <xref:System.Runtime.Serialization.DataMemberAttribute> y <xref:System.Runtime.Serialization.DataContractAttribute>.  
  
 El cliente es una aplicación de consola \(.exe\) e Internet Information Services \(IIS\) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La clase `ServiceContract` se utiliza en la clase `ComplexNumber`.El tipo `ComplexNumber` no tiene los atributos <xref:System.Runtime.Serialization.DataMemberAttribute> y <xref:System.Runtime.Serialization.DataContractAttribute>, como se muestra en el siguiente código de ejemplo.De manera predeterminada, se serializan todas las propiedades y campos públicos.  
  
```  
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
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## Vea también  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>   
 [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md)