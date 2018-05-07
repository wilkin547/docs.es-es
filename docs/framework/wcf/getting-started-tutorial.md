---
title: Introducción a SimulationTutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 4a095e5391f3b532211b82a190c7010f41283e31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="getting-started-tutorial"></a>Tutorial de introducción
Los temas contenidos en esta sección están diseñados para ofrecerle una visión rápida a la Windows Communication Foundation (WCF) experiencia de programación. Están diseñados para ser completados en el orden en que aparecen en la lista incluida al final de este tema. Este tutorial constituye una introducción a los pasos necesarios para crear aplicaciones de cliente y servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Un servicio expone uno o más puntos de conexión, donde cada uno de ellos expone una o más operaciones de servicio. El *extremo* especifica una dirección donde se puede encontrar el servicio, un enlace que contiene la información que describe cómo un cliente debe comunicar con el servicio y un contrato que define la funcionalidad de un servicio proporciona el servicio a sus clientes.  
  
 Después de ver por orden los temas de este tutorial, dispondrá de un servicio en funcionamiento y un cliente que llama al servicio. Los tres primeros temas describen cómo definir un contrato de servicio, cómo implementar el contrato de servicio y cómo hospedar el servicio. El servicio que se crea está autohospedado en una aplicación de consola. Los servicios también se pueden hospedar en Internet Information Services (IIS). Para obtener más información acerca de cómo hacerlo, consulte [Cómo: hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). El servicio se configura en código; sin embargo, los servicios también se pueden configurar dentro de un archivo de configuración. Para obtener más información sobre el uso de un archivo de configuración, consulte [configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 Los tres temas siguientes describen cómo crear un proxy de cliente, configurar la aplicación cliente y usar el proxy de cliente para llamar a la operación de servicio expuesta por el servicio. Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] automatiza el proceso de tener acceso a estos metadatos y lo usa para construir y configurar la aplicación cliente para el servicio. Si no usas [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], puede usar el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para construir y configurar la aplicación de cliente para el servicio.  
  
 En todos los temas de esta sección se asume que está usando Visual Studio 2011 como entorno de desarrollo. Si está utilizando otro entorno de desarrollo, omita las instrucciones específicas de Visual Studio.  
  
> [!NOTE]
>  Si está ejecutando [!INCLUDE[wv](../../../includes/wv-md.md)] o versiones posteriores del sistema operativo Windows, debe iniciar Visual Studio, vaya al menú Inicio y haga clic en Visual Studio 2011 y seleccione **ejecutar como administrador**. Iniciar Visual Studio 2011 siempre como un administrador puede crear un acceso directo, haga clic en el acceso directo, seleccione Propiedades, seleccione la **compatibilidad** ficha y compruebe el **ejecutar este programa como administrador** casilla de verificación. Al iniciar Visual Studio 2011 con este acceso directo, siempre se ejecutará con derechos de administrador.  
  
 Para las aplicaciones de ejemplo que se pueden descargar en el disco duro y ejecutaron, vea los temas de [ejemplos de Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91). De este tema, en concreto, consulte el [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Para obtener información más detallada acerca de cómo crear servicios y clientes, consulte [programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Describe cómo crear un contrato de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mediante una interfaz definida por el usuario. El contrato define la funcionalidad expuesta por el servicio.  
  
 [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Describe cómo implementar un contrato de servicio Una vez definido un contrato, se debe implementar con una clase de servicio.  
  
 [Procedimiento para hospedar y ejecutar un servicio básico](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Describe cómo configurar un punto de conexión para el servicio mediante código y cómo hospedarlo en una aplicación de consola. Para activarse, un servicio se debe configurar y hospedar dentro de un entorno de tiempo de ejecución. Este entorno crea el servicio y controla su contexto y duración.  
  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Describe cómo recuperar los metadatos usados para crear un cliente proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a partir de un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Este proceso usa la funcionalidad Agregar referencia de servicio dentro de Visual Studio 2011.  
  
 [Cómo configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Describe cómo configurar un cliente de WCF La configuración del cliente requiere especificar el punto de conexión que el cliente usa para tener acceso al servicio.  
  
 [Cómo utilizar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Describe cómo usar el proxy de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para invocar operaciones de servicio.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejemplos de Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>Vea también  
 [Información conceptual](../../../docs/framework/wcf/conceptual-overview.md)  
 [Guía de la documentación](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Detalles de las características de WCF](../../../docs/framework/wcf/feature-details/index.md)
