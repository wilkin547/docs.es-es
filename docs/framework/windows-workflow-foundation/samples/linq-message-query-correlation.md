---
title: "Correlación de consultas de mensajes LINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1207f371da5b447903e2846229860fd8c214a46e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linq-message-query-correlation"></a>Correlación de consultas de mensajes LINQ
Este ejemplo muestra cómo realizar una correlación basada en contenidos mediante una implementación de <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizada en contraposición a <xref:System.ServiceModel.XPathMessageQuery> proporcionado por el sistema.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizado, correlación basada en contenidos.  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo realizar una ampliación a partir de la clase base <xref:System.ServiceModel.Dispatcher.MessageQuery> para propósitos de correlación. La implementación personalizada, `LinqMessageQuery`, permite a los usuarios proporcionar un XName para encontrar dentro del mensaje utilizando XLinq. Los datos recuperados por la consulta se utilizan para formar la clave de correlación para enviar los mensajes a la instancia de flujo de trabajo adecuada.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP. Para ejecutar este ejemplo, correcto ACL de dirección URL debe agregarse (vea [configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más detalles), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas. Asegúrese de que su dominio y su nombre de usuario se sustituyen.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.  
  
    1.  Compile la solución.  
  
    2.  Establezca varios proyectos de inicio haciendo clic en la solución y seleccione **Establecer proyectos de inicio**. Agregar **servicio** y **cliente** (en ese orden) como varios proyectos de inicio.  
  
    3.  Ejecute la aplicación. La consola del cliente muestra un flujo de trabajo que envía un pedido y recibe el id. del pedido de compra y, a continuación, confirma el pedido. La ventana Servicio mostrará las solicitudes que se están procesando.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
