---
title: Utilizar la propiedad AutomationID
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutomationId property
- UI Automation, AutomationId property
- properties, AutomationId
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
ms.openlocfilehash: 43a67a8dd73931172a6fa729c054ad494b29134e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800306"
---
# <a name="use-the-automationid-property"></a>Utilizar la propiedad AutomationID
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene escenarios y código de ejemplo que muestran cómo y cuándo puede usarse el elemento <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> para buscar un elemento dentro del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> identifica de manera única un elemento de Automatización de la interfaz de usuario de sus elementos del mismo nivel. Para más información sobre los identificadores de propiedad relacionados con la identificación de controles, vea [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> no garantiza una identidad única para todo el árbol; normalmente se necesita información de ámbito y de contenedor para ser útil. Por ejemplo, una aplicación puede contener un control de menú con varios elementos de menú de nivel superior que, a su vez, tienen varios elementos de menú secundarios. Estos elementos de menú secundarios pueden identificarse mediante un esquema genérico como "Elemento1", "Elemento2", etc., lo que permite identificadores duplicados para elementos secundarios en los elementos del menú de nivel superior.  
  
## <a name="scenarios"></a>Escenarios  
 Se han identificado tres escenarios principales de aplicación de cliente de Automatización de la interfaz de usuario que requieren el uso de <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> para conseguir resultados precisos y coherentes cuando se buscan elementos.  
  
> [!NOTE]
> Todos los elementos de Automatización de la interfaz de usuario admiten<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> en la vista de control con la excepción de las ventanas de aplicación de nivel superior, los elementos de Automatización de la interfaz de usuario derivados de controles [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] que no tienen un identificador o un elemento x:Uid, y los elementos de Automatización de la interfaz de usuario derivados de controles [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] que no tienen un identificador de control.  
  
#### <a name="use-a-unique-and-discoverable-automationid-to-locate-a-specific-element-in-the-ui-automation-tree"></a>Usar un valor de AutomationID único y reconocible para buscar un elemento concreto en el árbol de Automatización de la interfaz de usuario  
  
- Use una herramienta como UI Spy para notificar el <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> de un elemento de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] de interés. Este valor se puede copiar y pegar en una aplicación cliente, como un script de prueba para las pruebas automatizadas posteriores. Este método reduce y simplifica el código necesario para identificar y buscar un elemento en tiempo de ejecución.  
  
> [!CAUTION]
> En general, debe intentar obtener solo elementos secundarios directos del elemento <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo que posiblemente provocaría un desbordamiento de pila. Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### <a name="use-a-persistent-path-to-return-to-a-previously-identified-automationelement"></a>Usar una ruta de acceso persistente para volver a un elemento AutomationElement previamente identificado  
  
- Las aplicaciones cliente, desde los scripts de prueba simples a las utilidades robustas de registro y reproducción, pueden requerir acceso a elementos de los que actualmente no haya instancias, como un diálogo de apertura de archivo o un elemento de menú y, por tanto, no existen en el árbol de Automatización de la interfaz de usuario. Solo se pueden crear instancias de estos elementos mediante la reproducción de una secuencia concreta de acciones de la interfaz de usuario a través del uso de propiedades de automatización de la interfaz de usuario como AutomationID, patrones de control y agentes de escucha de eventos.
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### <a name="use-a-relative-path-to-return-to-a-previously-identified-automationelement"></a>Usar una ruta de acceso relativa para volver a un elemento AutomationElement previamente identificado  
  
- En ciertas circunstancias, como solo se garantiza que AutomationID es único entre elementos del mismo nivel, varios elementos del árbol de Automatización de la interfaz de usuario pueden tener valores de propiedad AutomationID idénticos. En estos casos, los elementos se pueden identificar de forma única en función de un elemento primario y, si es necesario, un elemento primario del primario. Por ejemplo, un desarrollador puede proporcionar una barra de menús con varios elementos de menú, cada uno de ellos con varios elementos de menú secundarios donde se identifican los elementos secundarios con elementos AutomationID secuenciales como "Elemento1", "Elemento2" y así sucesivamente. Cada elemento de menú podría, por tanto, identificarse de forma única por su AutomationID junto con el AutomationID de su elemento primario y, si es necesario, el elemento primario de su primario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>
- [Información general sobre el árbol de la Automatización de la interfaz de usuario](ui-automation-tree-overview.md)
- [Búsqueda de un elemento de Automatización de la interfaz de usuario basada en una condición de propiedad](find-a-ui-automation-element-based-on-a-property-condition.md)
