---
title: Introducción a SimulationTutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: e5a07e5264c715f568121403721a3c844b903d99
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553082"
---
# <a name="getting-started-tutorial"></a>Tutorial de introducción
Los temas contenidos en esta sección están diseñados para proporcionarle una visión rápida a la Windows Communication Foundation (WCF) experiencia de programación. Están diseñados para ser completados en el orden en que aparecen en la lista incluida al final de este tema. Este tutorial le ofrece una introducción a los pasos necesarios para la creación de aplicaciones cliente y el servicio WCF. Un servicio expone uno o más puntos de conexión, donde cada uno de ellos expone una o más operaciones de servicio. El *extremo* especifica una dirección donde se puede encontrar el servicio, un enlace que contiene la información que describe cómo un cliente debe comunicar con el servicio y un contrato que define la funcionalidad de un servicio proporciona el servicio a sus clientes.  
  
 Después de ver por orden los temas de este tutorial, dispondrá de un servicio en funcionamiento y un cliente que llama al servicio. Los tres primeros temas describen cómo definir un contrato de servicio, cómo implementar el contrato de servicio y cómo hospedar el servicio. El servicio que se crea está autohospedado en una aplicación de consola. Los servicios también se pueden hospedar en Internet Information Services (IIS). Para obtener más información acerca de cómo hacerlo, consulte [Cómo: hospedar un servicio WCF en IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). El servicio se configura en código; sin embargo, los servicios también se pueden configurar dentro de un archivo de configuración. Para obtener más información sobre el uso de un archivo de configuración, consulte [configurar servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 Los tres temas siguientes describen cómo crear un proxy de cliente, configurar la aplicación cliente y usar el proxy de cliente para llamar a la operación de servicio expuesta por el servicio. Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] automatiza el proceso de tener acceso a estos metadatos y lo usa para construir y configurar la aplicación cliente para el servicio. Si no usas [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], puede usar el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para construir y configurar la aplicación cliente para el servicio.  
  
 En todos los temas de esta sección se asume que está usando Visual Studio 2011 como entorno de desarrollo. Si usa otro entorno de desarrollo, omita las instrucciones específicas de Visual Studio.  
  
> [!NOTE]
>  Si está ejecutando [!INCLUDE[wv](../../../includes/wv-md.md)] o versiones posteriores del sistema operativo Windows, debe iniciar Visual Studio, vaya al menú Inicio y a la derecha, haga clic en Visual Studio 2011 y seleccione **ejecutar como administrador**. Para iniciar Visual Studio 2011 siempre como administrador puede crear un acceso directo, a la derecha, haga clic en el acceso directo, seleccione Propiedades, seleccione la **compatibilidad** pestaña y compruebe el **ejecutar este programa como administrador** casilla de verificación. Al iniciar Visual Studio 2011 con este acceso directo, siempre se ejecutará con derechos de administrador.  
  
 Para aplicaciones de ejemplo que pueden descargarse en el disco duro y ejecutarse, vea los temas de [ejemplos de Windows Communication Foundation](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91). Este tema, consulte, en particular, el [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Para obtener información más detallada sobre la creación de servicios y clientes, consulte [programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo definir un contrato de servicios](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Describe cómo crear un contrato WCF mediante una interfaz definida por el usuario. El contrato define la funcionalidad expuesta por el servicio.  
  
 [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Describe cómo implementar un contrato de servicio Una vez definido un contrato, se debe implementar con una clase de servicio.  
  
 [Procedimiento para hospedar y ejecutar un servicio básico](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Describe cómo configurar un punto de conexión para el servicio mediante código y cómo hospedarlo en una aplicación de consola. Para activarse, un servicio se debe configurar y hospedar dentro de un entorno de tiempo de ejecución. Este entorno crea el servicio y controla su contexto y duración.  
  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Describe cómo recuperar los metadatos usados para crear a un proxy de cliente WCF desde un servicio WCF. Este proceso usa la funcionalidad Agregar referencia de servicio dentro de Visual Studio 2011.  
  
 [Cómo configurar un cliente](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Describe cómo configurar un cliente de WCF La configuración del cliente requiere especificar el punto de conexión que el cliente usa para tener acceso al servicio.  
  
 [Cómo utilizar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Describe cómo usar al proxy de cliente WCF para invocar operaciones de servicio.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ejemplos de Windows Communication Foundation](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>Vea también  
 [Información conceptual](../../../docs/framework/wcf/conceptual-overview.md)  
 [Guía de la documentación](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Detalles de las características de WCF](../../../docs/framework/wcf/feature-details/index.md)
