---
title: "Correlaci&#243;n de consultas de mensajes LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Correlaci&#243;n de consultas de mensajes LINQ
Este ejemplo muestra cómo realizar una correlación basada en contenidos mediante una implementación de <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizada en contraposición a <xref:System.ServiceModel.XPathMessageQuery> proporcionado por el sistema.  
  
## Demostraciones  
 <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizado, correlación basada en contenidos.  
  
## Análisis  
 En este ejemplo se muestra cómo realizar una ampliación a partir de la clase base <xref:System.ServiceModel.Dispatcher.MessageQuery> para propósitos de correlación.La implementación personalizada, `LinqMessageQuery`, permite a los usuarios proporcionar un XName para encontrar dentro del mensaje utilizando XLinq.Los datos recuperados por la consulta se utilizan para formar la clave de correlación para enviar los mensajes a la instancia de flujo de trabajo adecuada.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  En este ejemplo se expone un servicio del flujo de trabajo mediante extremos HTTP.Para realizar este ejemplo, se deben agregar listas de control de acceso de dirección URL adecuadas \(vea [Configuración de HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información\) ejecutando Visual Studio como administrador o el siguiente comando en una ventana de símbolo del sistema elevado para agregar las listas de control de acceso adecuadas.Asegúrese de que su dominio y su nombre de usuario se sustituyen.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.  
  
    1.  Compile la solución.  
  
    2.  Establezca varios proyectos de inicio haciendo clic con el botón secundario en la solución y seleccionando **Establecer proyectos de inicio**.Agregue **Servicio** y **Cliente** \(en ese orden\) como proyectos de inicio múltiple.  
  
    3.  Ejecute la aplicación.La consola del cliente muestra un flujo de trabajo que envía un pedido y recibe el id. del pedido de compra y, a continuación, confirma el pedido.La ventana Servicio mostrará las solicitudes que se están procesando.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`