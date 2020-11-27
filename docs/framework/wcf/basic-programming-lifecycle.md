---
title: Ciclo de vida de programación básica
description: Obtenga información sobre las tareas para compilar una aplicación WCF. WCF permite que las aplicaciones se comuniquen en el mismo equipo, a través de redes o en distintas plataformas de aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: f958bd06f617a5648b31332ebe9e7662d45cd241
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294851"
---
# <a name="basic-programming-lifecycle"></a>Ciclo de vida de programación básica

Windows Communication Foundation (WCF) permite a las aplicaciones comunicar si están en el mismo equipo, a través de Internet o en distintas plataformas de aplicación. En este tema se describen las tareas necesarias para compilar una aplicación WCF. Para obtener una aplicación de ejemplo en funcionamiento, vea el [tutorial de introducción](getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Las tareas básicas  

 Las tareas básicas que se van a realizar son, en orden:  
  
1. Definir el contrato de servicios. Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente. Para obtener más información, consulte [Designing Service Contracts](designing-service-contracts.md).  
  
2. Implementar el contrato. Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución. Para obtener más información, consulte [implementación de contratos de servicio](implementing-service-contracts.md).  
  
3. Configurar el servicio especificando los puntos de conexión y el resto de la información de comportamiento. Para obtener más información, vea [configuración de servicios](configuring-services.md).  
  
4. Hospedar el servicio. Para obtener más información, vea [servicios de hospedaje](hosting-services.md).  
  
5. Compilar una aplicación cliente. Para obtener más información, consulte [Building clients](building-clients.md).  
  
 Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio. Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5. O si está creando un servicio que usarán otros, puede omitir el paso 5.  
  
 Una vez que esté familiarizado con el desarrollo de contratos de servicio, también puede leer la [Introducción a la extensibilidad](introduction-to-extensibility.md). Si tiene problemas con el servicio, consulte la guía de [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md) para ver si otros tienen problemas o similares.  
  
## <a name="see-also"></a>Vea también

- [Implementación de contratos de servicio](implementing-service-contracts.md)
