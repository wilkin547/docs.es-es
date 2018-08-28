---
title: Modelo de configuración jerárquica
ms.date: 03/30/2017
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
ms.openlocfilehash: ce0bc69424495594e0ee9c6b950a5fa9c4d5f993
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000106"
---
# <a name="hierarchical-configuration-model"></a>Modelo de configuración jerárquica
En este ejemplo se muestra cómo implementar una jerarquía de archivos de configuración para los servicios. También muestra cómo se heredan los enlaces, los comportamientos de servicio y los comportamientos de punto de conexión de los niveles superiores de la jerarquía.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Una de las características desarrolladas para WCF en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] es la mejora en el modelo de configuración jerárquica. Un ejemplo de modelo de configuración jerárquico sería el definido por Machine.config -> Rootweb.config -> Web.config. En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], los enlaces y comportamientos que se definen en los niveles superiores en la jerarquía de configuración se agrega a sus servicios sin una configuración explícita. En este ejemplo se muestra cómo es posible simplificar la configuración de servicio basándose en los elementos de configuración definidos en el nivel de equipo o aplicación.  
  
 Este ejemplo consta de nueve servicios, definidos en tres niveles de jerarquía. `Service1` está en la raíz. `Service2` y `Service3` heredan los elementos predeterminados de `Service1`. `Service4`, `Service5`, `Service6` y `Service7` se definen en un tercer nivel de la jerarquía y heredan los elementos predeterminados de `Service3`. Finalmente, `Service10` y `Service11` están en el cuarto nivel de la jerarquía.  
  
 Todos los servicios implementan el contrato `IDesc`. La siguiente definición corresponde a la interfaz `IDesc` que muestra los métodos expuestos en esta interfaz. La interfaz `IDesc` se define en Service1.cs.  
  
```csharp  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 La implementación de estos métodos por parte de los servicios es sencilla. `ListEndpoints` recorre todos las extremos de servicio y devuelve una lista de todos los extremos que el servicio tiene. `ListServiceBehaviors` recorre todos los comportamientos agregados al servicio y devuelve la lista de todos los comportamientos de servicio asociados al servicio. `ListEndpointBehaviors` se comporta de forma similar a `ListServiceBehaviors`, pero devuelve la lista de comportamientos de extremo en su lugar.  
  
 Esta implementación permite al cliente saber cuántos extremos expone el servicio y qué comportamientos de servicio y de extremo se han agregado al servicio. El cliente implementado como parte del ejemplo agrega una referencia de servicio a todos los servicios en la solución y muestra estos elementos para cada uno de los servicios.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
#### <a name="to-run-the-client"></a>Para ejecutar el cliente  
  
1.  Mediante [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo ConfigHierarchicalModel.sln.  
  
2.  El proyecto de cliente aún no está configurado como proyecto de inicio; siga estos pasos.  
  
    1.  En **el Explorador de soluciones**, haga clic en la solución y, a continuación, seleccione **propiedades**.  
  
    2.  En **propiedades comunes**, seleccione **proyecto de inicio**y, a continuación, haga clic en **proyecto de inicio único**.  
  
    3.  Desde el **proyecto de inicio único** lista desplegable, seleccione **cliente**.  
  
    4.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3.  Para generar el ejemplo, presione Ctrl+Mayús+B.  
  
4.  Para ejecutar el cliente, presione Ctrl+F5.  
  
> [!NOTE]
>  Si estos pasos no funcionan, asegúrese de que el entorno ha se ha establecido correctamente, mediante los siguientes pasos:  
>   
> 1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
> 2.  Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](building-the-samples.md).  
> 3.  Para ejecutar el ejemplo en una o varias configuraciones de equipo, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de administración de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193960)
