---
title: 'Tutorial: Introducción a las aplicaciones de Windows Communication Foundation'
description: Estos tutoriales proporcionan una introducción para crear aplicaciones WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184122"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Introducción a las aplicaciones de Windows Communication Foundation
La siguiente serie de tutoriales le presenta la experiencia de programación de Windows Communication Foundation (WCF). Trabajar a través de estos tutoriales en orden le dará una comprensión introductoria de los pasos necesarios para crear aplicaciones WCF. Una vez que haya terminado, tendrá un servicio WCF en ejecución y un cliente WCF que llama al servicio.

En el tutorial se supone que usa Visual Studio como entorno de desarrollo. Si usa otro entorno de desarrollo, ignore las instrucciones específicas de Visual Studio.

Para obtener ejemplos de aplicaciones WCF que puede descargar y ejecutar, vea [ejemplos de Windows Communication Foundation](samples/index.md). Para obtener una introducción a los ejemplos, consulte [Introducción](samples/getting-started-sample.md)al ejemplo .

Para obtener información más detallada acerca de la creación de servicios y clientes, vea [Programación básica de WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Tutoriales de WCF

Los tres primeros tutoriales describen cómo definir un contrato de servicio WCF, cómo implementarlo y cómo hospedarlo. El servicio que cree es autohospedado dentro de una aplicación de consola. También puede hospedar servicios en Microsoft Internet Information Services (IIS). Para obtener más información, vea [Cómo: hospedar un servicio WCF en IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Aunque use código para configurar el servicio en el tutorial, también puede configurar servicios dentro de un archivo de [configuración.](configuring-services-using-configuration-files.md)

- [Tutorial: Definir un contrato de servicio](how-to-define-a-wcf-service-contract.md)

    Crear un contrato WCF con una interfaz definida por el usuario. Este contrato define la funcionalidad que expone el servicio.

- [Tutorial: Implementar un contrato de servicio](how-to-implement-a-wcf-contract.md)

    Después de definir un contrato, debe implementarlo con una clase de servicio.

- [Tutorial: Hospedar y ejecutar un servicio básico](how-to-host-and-run-a-basic-wcf-service.md)

    Configure un punto de conexión para el servicio y hospede el servicio en una aplicación de consola. Para que un servicio se active, debe configurarlo y hospedarlo en un entorno en tiempo de ejecución. Este entorno en tiempo de ejecución crea el servicio y controla su contexto y duración.

Los dos tutoriales siguientes describen cómo crear, configurar y usar una aplicación cliente para llamar a las operaciones que expone el servicio. Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio. Visual Studio automatiza el proceso de acceso a estos metadatos y lo usa para construir la aplicación cliente para el servicio. Si decide no usar Visual Studio, puede usar la herramienta De la utilidad de metadatos de [ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) en su lugar.

- [Tutorial: Crear un cliente](how-to-create-a-wcf-client.md)

    Recuperar metadatos para crear un proxy de cliente WCF desde un servicio WCF. Los metadatos se recuperan mediante Visual Studio para agregar una referencia de servicio o puede usar la herramienta Utilidad de metadatos de ServiceModel. Especifique el punto de conexión que utiliza el cliente para tener acceso al servicio.

- [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md)

    Use el proxy de cliente WCF para llamar a las operaciones de servicio.

## <a name="reference"></a>Referencia

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Consulte también

- [Visión general conceptual](conceptual-overview.md)
- [Guía de la documentación](guide-to-the-documentation.md)
- [Qué es Windows Communication Foundation](whats-wcf.md)
- [Detalles de la característica WCF](feature-details/index.md)
- [Ciclo de vida de programación básico](basic-programming-lifecycle.md)
- [Construyendo clientes](building-clients.md)
- [Programación básica de WCF](basic-wcf-programming.md)
- [Cómo: Crear un contrato dúplex](feature-details/how-to-create-a-duplex-contract.md)
- [Cómo: Acceder a servicios con un contrato dúplex](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo: Usar Svcutil.exe para descargar documentos de metadatos](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Uso de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)
- [Muestra de introducción](samples/getting-started-sample.md)
- [Ejemplos de Windows Communication Foundation](samples/index.md)
- [Probar internamente](samples/self-host.md)
