---
title: Ciclo de vida de programación básica
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: 6d9ea3b877e7c735cf789039b2a6956037372888
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330563"
---
# <a name="basic-programming-lifecycle"></a>Ciclo de vida de programación básica
Windows Communication Foundation (WCF) permite a las aplicaciones comunicar si están en el mismo equipo, a través de Internet o en diferentes plataformas de aplicaciones. En este tema se describe las tareas necesarias para crear una aplicación de WCF. Para una aplicación de ejemplo funcional, consulte [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Las tareas básicas  
 Las tareas básicas que se van a realizar son, en orden:  
  
1. Definir el contrato de servicios. Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente. Para obtener más información, consulte [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2. Implementar el contrato. Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución. Para obtener más información, consulte [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3. Configurar el servicio especificando los puntos de conexión y el resto de la información de comportamiento. Para obtener más información, consulte [configurar Services](../../../docs/framework/wcf/configuring-services.md).  
  
4. Hospedar el servicio. Para obtener más información, consulte [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
5. Compilar una aplicación cliente. Para obtener más información, consulte [generar clientes](../../../docs/framework/wcf/building-clients.md).  
  
 Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio. Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5. O si está creando un servicio que usarán otros, puede omitir el paso 5.  
  
 Una vez que esté familiarizado con el desarrollo de contratos de servicio, también puede leer [Introducción a la extensibilidad](../../../docs/framework/wcf/introduction-to-extensibility.md). Si tiene problemas con su servicio, consulte [inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) para ver si otros tienen los problemas de iguales o similares.  
  
## <a name="see-also"></a>Vea también

- [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)
