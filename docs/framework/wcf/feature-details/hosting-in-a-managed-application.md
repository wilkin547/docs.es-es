---
title: Hospedaje en una aplicación administrada
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 759257edf89d1af5c453bb98f41361b54cf113ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597350"
---
# <a name="hosting-in-a-managed-application"></a>Hospedaje en una aplicación administrada
Los servicios Windows Communication Foundation (WCF) se pueden hospedar en cualquier aplicación .NET Framework. Los servicios autohospedados constituyen la opción de hospedaje más flexible porque es la que requiere una menor infraestructura para su implementación. Sin embargo, también es la opción de hospedaje menos robusta, porque las aplicaciones administradas no proporcionan las características avanzadas de hospedaje y administración de otras opciones de hospedaje en WCF, como Internet Information Services (IIS) y servicios de Windows.  
  
 Para crear un servicio autohospedado, cree y abra una instancia de <xref:System.ServiceModel.ServiceHost>, que inicia un servicio que realiza escuchas de mensajes. Para obtener más información, consulte [Cómo: hospedar un servicio WCF en una aplicación administrada](../how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Para obtener un ejemplo completo sobre cómo definir un contrato, implementar el contrato y hospedar un servicio dentro de una aplicación administrada, vea el [tutorial de introducción](../getting-started-tutorial.md) y el [propio host](../samples/self-host.md).  
  
 Las siguientes secciones describen escenarios comunes que utilizan esta opción de hospedaje.  
  
## <a name="console-applications"></a>Aplicaciones de consola  
 Los escenarios comunes que habilita el autohospedaje son servicios WCF que se ejecutan dentro de las aplicaciones de consola. Hospedar un servicio WCF dentro de una aplicación de consola suele ser útil durante la fase de desarrollo del servicio. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones.  
  
## <a name="rich-client-applications"></a>Aplicaciones de cliente complejas  
 Otros escenarios comunes que habilita el autohospedaje son las aplicaciones cliente enriquecidas, como las basadas en Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Esta opción de hospedaje también facilita que las aplicaciones cliente enriquecidas, como las aplicaciones de WPF y WinForms, se comuniquen con el mundo exterior. Por ejemplo, un cliente de colaboración punto a punto que usa WPF para su interfaz de usuario y también hospeda un servicio WCF que permite a otros clientes conectarse a él y compartir información.  
  
## <a name="see-also"></a>Vea también

- [Servicios de hospedaje](../hosting-services.md)
- [Tutorial de Introducción](../getting-started-tutorial.md)
