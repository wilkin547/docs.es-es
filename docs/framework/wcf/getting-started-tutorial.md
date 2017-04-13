---
title: "Tutorial de introducci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "introducción [WCF]"
  - "WCF [WCF], introducción"
  - "Windows Communication Foundation [WCF], introducción"
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# Tutorial de introducci&#243;n
Los temas contenidos en esta sección están pensados para ofrecerle una visión rápida a la programación en [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  Están diseñados para ser completados en el orden en que aparecen en la lista incluida al final de este tema.  Este tutorial constituye una introducción a los pasos necesarios para crear aplicaciones de cliente y servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Un servicio expone uno o más extremos, donde cada uno de ellos expone una o más operaciones de servicio.  El *extremo* de un servicio especifica una dirección donde se puede encontrar el servicio, un enlace que contiene la información que describe cómo un cliente debe comunicar con el servicio y un contrato que define la funcionalidad proporcionada por el servicio a sus clientes.  
  
 Después de ver por orden los temas de este tutorial, dispondrá de un servicio en funcionamiento y un cliente que llama al servicio.  Los tres primeros temas describen cómo definir un contrato de servicio, cómo implementar el contrato de servicio y cómo hospedar el servicio.  El servicio que se crea está autohospedado en una aplicación de consola.  Los servicios también se pueden hospedar en Internet Information Services \(IIS\).  [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo hacerlo, vea [Procedimiento para hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  El servicio se configura en código; sin embargo, los servicios también se pueden configurar dentro de un archivo de configuración.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo usar un archivo de configuración, vea [Configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 Los tres temas siguientes describen cómo crear un proxy de cliente, configurar la aplicación cliente y usar el proxy de cliente para llamar a la operación de servicio expuesta por el servicio.  Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] automatiza el proceso de tener acceso a estos metadatos y lo usa para construir y configurar la aplicación cliente para el servicio.  Si no está usando [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], puede usar [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para construir y configurar la aplicación cliente para el servicio.  
  
 En todos los temas de esta sección se asume que está usando Visual Studio 2011 como entorno de desarrollo.  Si está utilizando otro entorno de desarrollo, omita las instrucciones específicas para [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)].  
  
> [!NOTE]
>  Si está ejecutando [!INCLUDE[wv](../../../includes/wv-md.md)] o versiones posteriores del sistema operativo Windows, debe iniciar [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]; para ello, vaya al menú Inicio, haga clic con el botón secundario en Visual Studio 2011 y seleccione **Ejecutar como administrador**.  Para iniciar Visual Studio 2011 siempre como administrador, puede crear un acceso directo, hacer clic con el botón secundario en el acceso directo, seleccionar Propiedades, seleccionar la pestaña **Compatibilidad** y activar la casilla **Ejecutar este programa como administrador**.  Al iniciar Visual Studio 2011 con este acceso directo, siempre se ejecutará con derechos de administrador.  
  
 Para las aplicaciones de ejemplo que se pueden descargar a su disco duro y ejecutarse en él, consulte los temas en [Windows Communication Foundation Samples](http://msdn.microsoft.com/es-es/8ec9d192-5d81-4f64-bfd3-90c5e5858c91).  Para ver este tema, consulte, en particular, [Introducción:](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Para obtener información más detallada sobre la creación de servicios y clientes, vea [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## En esta sección  
 [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Describe cómo crear un contrato de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mediante una interfaz definida por el usuario.  El contrato define la funcionalidad expuesta por el servicio.  
  
 [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Describe cómo implementar un contrato de servicio  Una vez definido un contrato, se debe implementar con una clase de servicio.  
  
 [Procedimiento para hospedar y ejecutar un servicio básico](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Describe cómo configurar un extremo para el servicio mediante código y cómo hospedarlo en una aplicación de consola.  Para activarse, un servicio se debe configurar y hospedar dentro de un entorno de tiempo de ejecución.  Este entorno crea el servicio y controla su contexto y duración.  
  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Describe cómo recuperar los metadatos usados para crear un cliente proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a partir de un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Este proceso usa la funcionalidad Agregar referencia de servicio dentro de Visual Studio 2011.  
  
 [Cómo configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Describe cómo configurar un cliente de WCF La configuración del cliente requiere especificar el extremo que el cliente usa para tener acceso al servicio.  
  
 [Cómo utilizar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Describe cómo usar el proxy de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para invocar operaciones de servicio.  
  
## Referencia  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## Secciones relacionadas  
 [Windows Communication Foundation Samples](http://msdn.microsoft.com/es-es/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## Vea también  
 [Información conceptual](../../../docs/framework/wcf/conceptual-overview.md)   
 [Guía de la documentación](../../../docs/framework/wcf/guide-to-the-documentation.md)   
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)   
 [Detalles de las características de WCF](../../../docs/framework/wcf/feature-details/index.md)