---
title: 'Tutorial: Introducción a las aplicaciones Windows Communication Foundation'
description: Estos tutoriales proporcionan una introducción a la creación de aplicaciones WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238241"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Introducción a las aplicaciones Windows Communication Foundation

La siguiente serie de tutoriales presenta la experiencia de programación de Windows Communication Foundation (WCF). Al trabajar con estos tutoriales en orden se ofrece una introducción a los pasos necesarios para crear aplicaciones WCF. Una vez finalizado, tendrá un servicio WCF en ejecución y un cliente de WCF que llama al servicio.

En el tutorial se supone que usa Visual Studio como entorno de desarrollo. Si usa otro entorno de desarrollo, omita las instrucciones específicas de Visual Studio.

Para ver las aplicaciones WCF de ejemplo que puede descargar y ejecutar, consulte [ejemplos de Windows Communication Foundation](samples/index.md). Para obtener una introducción a los ejemplos, consulte [ejemplo de introducción](samples/getting-started-sample.md).

Para obtener información más detallada sobre la creación de servicios y clientes, vea [programación básica de WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Tutoriales de WCF

Los tres primeros tutoriales describen cómo definir un contrato de servicio de WCF, cómo implementarlo y cómo hospedarlo. El servicio que cree se autohospeda en una aplicación de consola. También puede hospedar servicios en Microsoft Internet Information Services (IIS). Para obtener más información, consulte [How to: host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Aunque use código para configurar el servicio en el tutorial, también puede configurar los [servicios dentro de un archivo de configuración](configuring-services-using-configuration-files.md).

- [Tutorial: definición de un contrato de servicios](how-to-define-a-wcf-service-contract.md)

    Cree un contrato de WCF con una interfaz definida por el usuario. Este contrato define la funcionalidad que expone el servicio.

- [Tutorial: implementar un contrato de servicios](how-to-implement-a-wcf-contract.md)

    Después de definir un contrato, debe implementarlo con una clase de servicio.

- [Tutorial: hospedar y ejecutar un servicio básico](how-to-host-and-run-a-basic-wcf-service.md)

    Configure un punto de conexión para el servicio y hospede el servicio en una aplicación de consola. Para que un servicio se active, debe configurarlo y hospedarlo en un entorno en tiempo de ejecución. Este entorno de tiempo de ejecución crea el servicio y controla su contexto y duración.

En los dos tutoriales siguientes se describe cómo crear, configurar y usar una aplicación cliente para llamar a las operaciones que expone el servicio. Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio. Visual Studio automatiza el proceso de acceso a estos metadatos y lo usa para construir la aplicación cliente para el servicio. Si decide no usar Visual Studio, puede usar la [herramienta de utilidad de metadatos de ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) en su lugar.

- [Tutorial: creación de un cliente](how-to-create-a-wcf-client.md)

    Recuperar metadatos para crear un proxy de cliente de WCF desde un servicio WCF. Los metadatos se recuperan mediante Visual Studio para agregar una referencia de servicio o se puede usar la herramienta de utilidad de metadatos de ServiceModel. Especifique el punto de conexión que el cliente utiliza para tener acceso al servicio.

- [Tutorial: uso de un cliente](how-to-use-a-wcf-client.md)

    Use el proxy de cliente de WCF para llamar a las operaciones de servicio.

## <a name="reference"></a>Referencia

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Vea también

- [Información general conceptual](conceptual-overview.md)
- [Guía de la documentación](guide-to-the-documentation.md)
- [Qué es Windows Communication Foundation](whats-wcf.md)
- [Detalles de las características de WCF](feature-details/index.md)
- [Ciclo de vida de programación básica](basic-programming-lifecycle.md)
- [Compilar clientes](building-clients.md)
- [Programación básica de WCF](basic-wcf-programming.md)
- [Cómo: crear un contrato dúplex](feature-details/how-to-create-a-duplex-contract.md)
- [Cómo: obtener acceso a los servicios con un contrato dúplex](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo: usar Svcutil.exe para descargar documentos de metadatos](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Cómo: publicar metadatos para un servicio mediante un archivo de configuración](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Uso de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)
- [Ejemplo de introducción](samples/getting-started-sample.md)
- [Ejemplos de Windows Communication Foundation](samples/index.md)
- [Probar internamente](samples/self-host.md)
