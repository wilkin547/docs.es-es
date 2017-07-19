---
title: "Sesi&#243;n de confianza de WS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Sesión de confianza"
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Sesi&#243;n de confianza de WS
Este ejemplo muestra el uso de la sesión de confianza. Las sesiones de confianza proporcionan compatibilidad para la mensajería y las sesiones de confianza.La mensajería de confianza reintenta la comunicación en caso de error y permite especificar garantías de entrega, como la llegada en orden de los mensajes.Las sesiones mantienen el estado de los clientes entre llamadas.El ejemplo implementa las sesiones para mantener el estado del cliente y especifica las convicciones de la entrega en orden.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 Este ejemplo se basa en el [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.Las características de sesión de confianza están habilitadas y configurados en los archivos de configuración de la aplicación para el cliente y el servicio.  
  
 En este ejemplo, el cliente es una aplicación de consola \(.exe\) y los Servicios de Internet Information Server \(IIS\) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo utiliza el archivo `wsHttpBinding`.El enlace se especifica en los archivos de configuración para el cliente y el servicio.El tipo de enlace se especifica en el atributo `binding` del elemento del extremo tal y como se explica en el ejemplo siguiente de configuración.  
  
```  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  
```  
  
 El extremo contiene un atributo `bindingConfiguration` que hace referencia a una configuración de enlace denominada "Binding1". La configuración de enlace habilita las sesiones de confianza estableciendo el atributo `enabled` de [\<\<reliableSession\>\>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) como `true`.Las convicciones de la entrega para las sesiones ordenadas se controlan estableciendo el atributo ordenado como `true` o `false`.El valor predeterminado es `true`.  
  
```  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
  
```  
  
 La clase de implementación de servicio implementa <xref:System.ServiceModel.InstanceContextMode> que crea instancias para mantener una instancia de clase independiente para cada cliente, como se muestra en el código muestra siguiente.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también