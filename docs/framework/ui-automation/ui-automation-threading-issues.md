---
title: Aspectos relacionados con subprocesos de la UI Automation
description: Obtenga información sobre problemas con el subprocesamiento de UI Automation. Por ejemplo, pueden producirse conflictos si una aplicación cliente intenta interactuar con su propia interfaz de usuario en el subproceso de la interfaz de usuario.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, threading issues
- threading issues with UI Automation
ms.assetid: 0ab8d42c-5b8b-481b-b788-2caecc2f0191
ms.openlocfilehash: 1f17336e6baa2e2baf4cd37a5b39bed913bd3bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258652"
---
# <a name="ui-automation-threading-issues"></a>Aspectos relacionados con subprocesos de la UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Debido a la forma en que [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] utiliza los mensajes de Windows, pueden producirse conflictos cuando una aplicación cliente intenta interactuar con su propia [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] en el subproceso [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Estos conflictos pueden dar lugar a un rendimiento muy lento o incluso provocar que la aplicación deje de responder.  
  
 Si la aplicación cliente está diseñada para interactuar con todos los elementos del escritorio, incluida su propia [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], debe realizar todas las llamadas a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] en un subproceso independiente. Esto incluye la ubicación de elementos (por ejemplo, mediante el método <xref:System.Windows.Automation.TreeWalker> o <xref:System.Windows.Automation.AutomationElement.FindAll%2A> ) y el uso de patrones de control.  
  
 Es seguro realizar llamadas a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dentro de un controlador de eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , porque siempre se llama al controlador de eventos en un subproceso no de[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . No obstante, al suscribirse a eventos que pueden provenir de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]de la aplicación cliente, debe realizar la llamada a <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>, o a un método relacionado, en un subproceso no de[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Quite los controladores de eventos que estén en el mismo subproceso.
