---
title: "Modelo de configuraci&#243;n jer&#225;rquica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Modelo de configuraci&#243;n jer&#225;rquica
En este ejemplo se muestra cómo implementar una jerarquía de archivos de configuración para los servicios.También muestra cómo se heredan los enlaces, los comportamientos de servicio y los comportamientos de extremo de los niveles superiores de la jerarquía.  
  
## Detalles del ejemplo  
 Una de las características desarrolladas para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] es la mejora del modelo de configuración jerárquico.Un ejemplo de modelo de configuración jerárquico sería el definido por Machine.config \-\> Rootweb.config \-\> Web.config.En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], los enlaces y comportamientos que se definen en los niveles superiores en la jerarquía de configuración se agrega a sus servicios sin una configuración explícita.En este ejemplo se muestra cómo es posible simplificar la configuración de servicio basándose en los elementos de configuración definidos en el nivel de equipo o aplicación.  
  
 Este ejemplo consta de nueve servicios, definidos en tres niveles de jerarquía.`Service1` está en la raíz.`Service2` y `Service3` heredan los elementos predeterminados de `Service1`.`Service4`, `Service5`, `Service6` y `Service7` se definen en un tercer nivel de la jerarquía y heredan los elementos predeterminados de `Service3`.Finalmente, `Service10` y `Service11` están en el cuarto nivel de la jerarquía.  
  
 Todos los servicios implementan el contrato `IDesc`.La siguiente definición corresponde a la interfaz `IDesc` que muestra los métodos expuestos en esta interfaz.La interfaz `IDesc` se define en Service1.cs.  
  
```  
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
  
 La implementación de estos métodos por parte de los servicios es sencilla.`ListEndpoints` recorre todos las extremos de servicio y devuelve una lista de todos los extremos que el servicio tiene.`ListServiceBehaviors` recorre todos los comportamientos agregados al servicio y devuelve la lista de todos los comportamientos de servicio asociados al servicio.`ListEndpointBehaviors` se comporta de forma similar a `ListServiceBehaviors`, pero devuelve la lista de comportamientos de extremo en su lugar.  
  
 Esta implementación permite al cliente saber cuántos extremos expone el servicio y qué comportamientos de servicio y de extremo se han agregado al servicio.El cliente implementado como parte del ejemplo agrega una referencia de servicio a todos los servicios en la solución y muestra estos elementos para cada uno de los servicios.  
  
## Para utilizar este ejemplo  
  
#### Para ejecutar el cliente  
  
1.  Mediante [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo ConfigHierarchicalModel.sln.  
  
2.  El proyecto de cliente aún no está configurado como proyecto de inicio; siga estos pasos.  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón secundario en la solución y seleccione **Propiedades**.  
  
    2.  En **Properties comunes**, seleccione **Proyecto de inicio** y, a continuación, haga clic en **Proyecto de inicio único**.  
  
    3.  En el cuadro desplegable **Proyecto de inicio único**, seleccione **Cliente**.  
  
    4.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3.  Para generar el ejemplo, presione Ctrl\+Mayús\+B.  
  
4.  Para ejecutar el cliente, presione Ctrl\+F5.  
  
> [!NOTE]
>  Si estos pasos no funcionan, asegúrese de que el entorno se ha configurado correctamente mediante los pasos siguientes.  
>   
>  1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
> 2.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
> 3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## Vea también  
 [Ejemplos de administración de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193960)