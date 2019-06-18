---
title: Hospedaje en una aplicación administrada
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 1895f6622f7c528979badd741f5994970bbd1a8c
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169795"
---
# <a name="hosting-in-a-managed-application"></a>Hospedaje en una aplicación administrada
Servicios de Windows Communication Foundation (WCF) se pueden hospedar en cualquier aplicación de .NET Framework. Los servicios autohospedados constituyen la opción de hospedaje más flexible porque es la que requiere una menor infraestructura para su implementación. Sin embargo, también es la opción de hospedaje menos robusta, porque las aplicaciones administradas no proporcionan hospedaje avanzado y características de administración de otras opciones de hospedaje de WCF, como los servicios de Internet Information Services (IIS) y Windows.  
  
 Para crear un servicio autohospedado, cree y abra una instancia de <xref:System.ServiceModel.ServiceHost>, que inicia un servicio que realiza escuchas de mensajes. Para obtener más información, vea [Cómo: Hospedar un servicio WCF en una aplicación administrada](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Para obtener un ejemplo completo sobre cómo definir un contrato, implemente el contrato y hospedar un servicio dentro de una aplicación administrada, consulte el [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md) y [autohospedaje](../../../../docs/framework/wcf/samples/self-host.md).  
  
 Las siguientes secciones describen escenarios comunes que utilizan esta opción de hospedaje.  
  
## <a name="console-applications"></a>Aplicaciones de consola  
 Escenarios comunes que habilita el autohospedaje son servicios WCF que se ejecutan dentro de las aplicaciones de consola. Hospedar un servicio WCF dentro de una aplicación de consola es suele ser útil durante la fase de desarrollo del servicio. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones.  
  
## <a name="rich-client-applications"></a>Aplicaciones de cliente complejas  
 Otros escenarios comunes que habilita el autohospedaje es aplicaciones cliente enriquecidas, como las basadas en Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Esta opción de hospedaje también facilita a las aplicaciones cliente enriquecidas, como las aplicaciones de WPF y WinForms para comunicarse con el exterior. Por ejemplo, un cliente de colaboración de punto a punto que usa WPF para su interfaz de usuario y también hospeda un servicio WCF que permite a otros clientes para conectarse a él y compartir información.  
  
## <a name="see-also"></a>Vea también

- [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)
- [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)
