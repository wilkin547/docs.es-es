---
title: Servicio solo XAML básico
ms.date: 03/30/2017
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
ms.openlocfilehash: f4f296a97b9c3093874c5ec8e05023e84b0af44a
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508033"
---
# <a name="basic-xaml-only-service"></a>Servicio solo XAML básico
En este ejemplo se muestra cómo crear un servicio solo XAML. El escenario es un servicio del diagnóstico de problemas relacionados con el coche. El servicio se implementa como un flujo de trabajo que hace una serie de preguntas al cliente para diagnosticar el problema. Hay dos tipos de problemas que el servicio puede diagnosticar (el coche no arranca o el aire acondicionado no funciona). El flujo de trabajo utiliza la plantilla de solicitud/respuesta del diseñador para exponer tres operaciones de servicio simples. El servicio se hospeda en IIS al crear un directorio virtual en IIS y copiar los archivos service1.xamlx y web.config en el directorio virtual; no se requiere ningún código compilado. De forma predeterminada en este ejemplo automáticamente copiará los archivos necesarios en el directorio virtual creado al seguir las instrucciones de configuración de los ejemplos de WCF y WF: [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) cuando se compila en Visual Studio 2010.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Ejecute la aplicación cliente generada en [directorio base de la solución] \Client\bin\debug.  
  
3.  La aplicación imprime las opciones; seleccione una. A continuación, la aplicación hace algunas preguntas, responda sí o no (utilizando las claves Y/N). Cuando el servicio ha terminado de diagnosticar los problemas, la aplicación imprime un diagnóstico.  
  
4.  La aplicación regresa a las opciones. Puede diagnosticar otro problema o salir la aplicación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`