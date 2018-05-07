---
title: Enrutamiento por cuerpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: e9a0c947a1dd7ac2a6c7af74baaa072aae67358c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="route-by-body"></a>Enrutamiento por cuerpo
Este ejemplo muestra cómo implementar un servicio que acepta los objetos de mensaje con cualquier acción SOAP. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora. El servicio implementa una operación `Calculate` única que acepta un parámetro de solicitud <xref:System.ServiceModel.Channels.Message> y devuelve una respuesta <xref:System.ServiceModel.Channels.Message>.  
  
 En este ejemplo, el cliente es una aplicación de consola (.exe) y el servicio se hospeda en IIS.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo muestra el envío de mensajes según el contenido del cuerpo. El mecanismo de envío mensaje integrada del modelo de servicio Windows Communication Foundation (WCF) se basa en las acciones del mensaje. Sin embargo, hay muchos servicios Web existentes que definen todas sus operaciones con Action="". Es imposible compilar un servicio basado en WSDL que siga enviando mensajes de solicitud según la información de Action. Este ejemplo muestra un contrato de servicios basado en WSDL (WSDL está contenido en Service.wsdl, que está incluido con el ejemplo). El contrato de servicio es la Calculadora, similar al utilizado en [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). Sin embargo, `[OperationContract]` especifica `Action=""` para todas las operaciones.  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 Con un contrato, un servicio exige un `DispatchByBodyBehavior` de comportamiento de distribución personalizado para permitir que los mensajes se distribuyan entre operaciones. Este comportamiento de distribución inicializa el `DispatchByBodyElementOperationSelector` selector de operaciones personalizado con una tabla de los nombres de operación con clave por QName de elementos contenedores respectivos. `DispatchByBodyElementOperationSelector` busca en la etiqueta de inicio del primer elemento secundario del cuerpo y selecciona la operación usando la tabla mencionada previamente.  
  
 El cliente utiliza un proxy generado automáticamente desde el WSDL exportado mediante el servicio [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 El hecho de que las acciones de todas las operaciones estén vacías no tiene ningún impacto en el código de cliente, salvo los parámetros Action en el proxy generado automáticamente.  
  
 El código de cliente realiza varios cálculos. Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
## <a name="see-also"></a>Vea también
