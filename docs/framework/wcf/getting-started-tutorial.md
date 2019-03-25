---
title: 'Tutorial: Introducción a las aplicaciones de Windows Communication Foundation'
description: Estos tutoriales se proporciona una introducción para crear aplicaciones de WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 66211cfcf2b742e43eccbefb2bc7c4bd1147b05b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408865"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Introducción a las aplicaciones de Windows Communication Foundation
La siguiente serie de tutoriales de introducción a la Windows Communication Foundation (WCF) experiencia de programación. Trabajar con estos tutoriales en orden le proporcionará una introducción a los pasos necesarios para crear aplicaciones WCF. Cuando termine, tendrá un servicio WCF y un cliente WCF que llama al servicio. 

El tutorial supone que está utilizando Visual Studio como entorno de desarrollo. Si usa otro entorno de desarrollo, omita las instrucciones específico de Visual Studio. 

Para aplicaciones de WCF de ejemplo que puede descargar y ejecutar, consulte [ejemplos de Windows Communication Foundation](samples/index.md). Para obtener una introducción a los ejemplos, vea [ejemplo Introducción](samples/getting-started-sample.md).

Para obtener información más detallada sobre la creación de servicios y clientes, consulte [programación básica de WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Tutoriales WCF

Los tres primeros tutoriales describen cómo definir un contrato de servicio WCF, cómo implementarlo y cómo hospedarlo. El servicio que crea está autohospedado en una aplicación de consola. También puede hospedar servicios en Microsoft Internet Information Services (IIS). Para obtener más información, vea [Cómo: Hospedar un servicio WCF en IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Aunque utilizar código para configurar el servicio en el tutorial, también puede [configurar servicios dentro de un archivo de configuración](configuring-services-using-configuration-files.md). 

- [Tutorial: Definir un contrato de servicio](how-to-define-a-wcf-service-contract.md)

    Crear un contrato de WCF con una interfaz definida por el usuario. Este contrato define la funcionalidad que expone el servicio.

- [Tutorial: Implementar un contrato de servicio](how-to-implement-a-wcf-contract.md)

    Después de definir un contrato, se debe implementar una clase de servicio.

- [Tutorial: Hospedar y ejecutar un servicio básico](how-to-host-and-run-a-basic-wcf-service.md)

    Configurar un punto de conexión para el servicio y hospedar el servicio en una aplicación de consola. Para un servicio se vuelva activo, debe configurarlo y hospedarlo en un entorno de tiempo de ejecución. Este entorno de tiempo de ejecución crea el servicio y controla su contexto y duración.

Los siguientes dos tutoriales describen cómo crear, configurar y expone el uso de una aplicación cliente para llamar a las operaciones del servicio. Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio. Visual Studio automatiza el proceso de obtener acceso a estos metadatos y lo usa para construir la aplicación cliente para el servicio. Si decide no usar Visual Studio, puede usar el [herramienta de utilidad de metadatos de ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) en su lugar.

- [Tutorial: Crear un cliente](how-to-create-a-wcf-client.md)

    Recuperar metadatos para crear a un proxy de cliente WCF desde un servicio WCF. Recuperar metadatos mediante Visual Studio para agregar una referencia de servicio o puede usar la herramienta de utilidad de metadatos de ServiceModel. Especifique el punto de conexión que el cliente utiliza para tener acceso al servicio.

- [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md)

    Usar al proxy de cliente WCF para llamar a las operaciones de servicio.

## <a name="reference"></a>Referencia

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Vea también

- [Información general conceptual](conceptual-overview.md)
- [Guía de la documentación](guide-to-the-documentation.md)
- [¿Qué es Windows Communication Foundation](whats-wcf.md)
- [Detalles de características WCF](feature-details/index.md)
- [Ciclo de vida de programación básica](basic-programming-lifecycle.md)
- [Creación de clientes](building-clients.md)
- [Programación básica de WCF](basic-wcf-programming.md)
- [Cómo: Crear un contrato dúplex](feature-details/how-to-create-a-duplex-contract.md)
- [Cómo: Servicios de Access con un contrato dúplex](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo: Utilice Svcutil.exe para descargar documentos de metadatos](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Utilización de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)
- [Ejemplo de introducción](samples/getting-started-sample.md)
- [Ejemplos de Windows Communication Foundation](samples/index.md)
- [Probar internamente](samples/self-host.md)


