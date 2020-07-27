---
title: Obtener elementos de UI Automation
description: Revise varias formas de obtener objetos de elemento de automatización de la interfaz de usuario (AutomationElement) para los elementos de la interfaz de usuario.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, obtaining elements
- elements, UI Automation, obtaining
ms.assetid: c2caaf45-e59c-42a1-bc9b-77a6de520171
ms.openlocfilehash: 2b741dde3b30334ba8fa990d73044da7e3bdd2da
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168158"
---
# <a name="obtaining-ui-automation-elements"></a>Obtener elementos de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se describen las distintas formas de obtener objetos <xref:System.Windows.Automation.AutomationElement> para elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .  
  
> [!CAUTION]
> Si la aplicación cliente intenta buscar elementos en su propia interfaz de usuario, debe realizar todos las llamadas a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] en un subproceso independiente. Para obtener más información, consulta [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
<a name="The_Root_Element"></a>
## <a name="root-element"></a>Elemento raíz  
 Todas las búsquedas de objetos <xref:System.Windows.Automation.AutomationElement> deben tener un punto de inicio. Puede ser cualquier elemento, incluidos el escritorio, una ventana de aplicación o un control.  
  
 El elemento raíz para el escritorio, del que descienden todos los elementos, se obtiene de la propiedad estática <xref:System.Windows.Automation.AutomationElement.RootElement%2A?displayProperty=nameWithType> .  
  
> [!CAUTION]
> En general, debe intentar obtener solo elementos secundarios directos del elemento <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo que posiblemente provocaría un desbordamiento de pila. Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.  
  
<a name="Using_Conditions"></a>
## <a name="conditions"></a>Condiciones  
 Para la mayoría de técnicas que puede usar para recuperar elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , debe especificar un elemento <xref:System.Windows.Automation.Condition>, que es un conjunto de criterios que definen los elementos que quiere recuperar.  
  
 La condición más simple es <xref:System.Windows.Automation.Condition.TrueCondition>, un objeto predefinido que especifica que se devolverán todos los elementos dentro del ámbito de búsqueda. <xref:System.Windows.Automation.Condition.FalseCondition>, que es el elemento opuesto de <xref:System.Windows.Automation.Condition.TrueCondition>, no es tan útil, ya que impediría que se encontraran elementos.  
  
 Hay otras tres condiciones predefinidas que se pueden utilizar por sí solas o en combinación con otras condiciones: <xref:System.Windows.Automation.Automation.ContentViewCondition>, <xref:System.Windows.Automation.Automation.ControlViewCondition>y <xref:System.Windows.Automation.Automation.RawViewCondition>. <xref:System.Windows.Automation.Automation.RawViewCondition>, por sí sola, equivale a <xref:System.Windows.Automation.Condition.TrueCondition>, porque no filtra los elementos por sus propiedades <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> o <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> .  
  
 Otras condiciones se componen de uno o varios objetos <xref:System.Windows.Automation.PropertyCondition> , cada uno de los cuales especifica un valor de propiedad. Por ejemplo, un elemento <xref:System.Windows.Automation.PropertyCondition> podría especificar que el elemento está habilitado o que admite un patrón de control determinado.  
  
 Las condiciones se pueden combinar con lógica booleana, mediante la construcción de objetos de tipos <xref:System.Windows.Automation.AndCondition>, <xref:System.Windows.Automation.OrCondition>y <xref:System.Windows.Automation.NotCondition>.  
  
<a name="Search_Scope"></a>
## <a name="search-scope"></a>Ámbito de búsqueda  
 Las búsquedas realizadas con <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> o <xref:System.Windows.Automation.AutomationElement.FindAll%2A> deben tener un ámbito así como un punto de inicio.  
  
 El ámbito define el espacio alrededor del punto de inicio en el que se va a buscar. Esto podría incluir el propio elemento, sus elementos relacionados, su elemento primario, sus antecesores, sus elementos secundarios inmediatos y sus descendientes.  
  
 El ámbito de una búsqueda se define mediante una combinación bit a bit de valores de la enumeración <xref:System.Windows.Automation.TreeScope> .  
  
<a name="Finding_a_Known_Element"></a>
## <a name="finding-a-known-element"></a>Búsqueda de un elemento conocido  
 Para buscar un elemento conocido, identificado por su <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>o alguna otra propiedad o combinación de propiedades, lo más fácil es utilizar el método <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> . Si el elemento que se busca es una ventana de aplicación, el punto inicial de la búsqueda puede ser el elemento <xref:System.Windows.Automation.AutomationElement.RootElement%2A>.  
  
 Esta forma de buscar elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es especialmente útil en escenarios de pruebas automatizadas.  
  
<a name="Finding_Elements_in_a_Subtree"></a>
## <a name="finding-elements-in-a-subtree"></a>Búsqueda de elementos en un subárbol  
 Para encontrar todos los elementos que cumplan criterios concretos relacionados con un elemento conocido, puede utilizar <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. Por ejemplo, podría utilizar este método para recuperar elementos de lista o elementos de menú de una lista o un menú, o para identificar todos los controles de un cuadro de diálogo.  
  
<a name="Walking_a_Subtree"></a>
## <a name="walking-a-subtree"></a>Recorrer un subárbol  
 Si no tiene conocimiento previo de las aplicaciones con las que se puede usar el cliente, puede construir un subárbol de todos los elementos de interés con la clase <xref:System.Windows.Automation.TreeWalker> . La aplicación podría hacer esto en respuesta a un evento de cambio de foco; es decir, cuando una aplicación o un control recibe el foco de entrada, el cliente de Automatización de la interfaz de usuario examina los elementos secundarios y quizás todos los descendientes del elemento en el que está el foco.  
  
 Otra forma en que se puede utilizar <xref:System.Windows.Automation.TreeWalker> es para identificar los antecesores de un elemento. Por ejemplo, al recorrer el árbol en sentido ascendente, se puede identificar la ventana primaria de un control.  
  
 Puede usar <xref:System.Windows.Automation.TreeWalker> mediante la creación de un objeto de la clase (definiendo los elementos de interés pasando un elemento <xref:System.Windows.Automation.Condition>) o mediante uno de los siguientes objetos predefinidos que se definen como campos de <xref:System.Windows.Automation.TreeWalker>.  
  
|||  
|-|-|  
|<xref:System.Windows.Automation.TreeWalker.ContentViewWalker>|Busca únicamente los elementos cuya propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> sea `true`.|  
|<xref:System.Windows.Automation.TreeWalker.ControlViewWalker>|Busca únicamente los elementos cuya propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> sea `true`.|  
|<xref:System.Windows.Automation.TreeWalker.RawViewWalker>|Busca todos los elementos.|  
  
 Después de haber obtenido un elemento <xref:System.Windows.Automation.TreeWalker>, su uso es sencillo. Basta con llamar a los métodos `Get` para navegar entre elementos del subárbol.  
  
 El método <xref:System.Windows.Automation.TreeWalker.Normalize%2A> puede utilizarse para desplazarse a un elemento del subárbol desde otro elemento que no forma parte de la vista. Por ejemplo, suponga que ha creado una vista de un subárbol mediante <xref:System.Windows.Automation.TreeWalker.ContentViewWalker>. Después, la aplicación recibe la notificación de que una barra de desplazamiento ha recibido el foco de entrada. Como una barra de desplazamiento no es un elemento de contenido, no está presente en la vista del subárbol. Sin embargo, puede pasar el elemento <xref:System.Windows.Automation.AutomationElement> que representa la barra de desplazamiento a <xref:System.Windows.Automation.TreeWalker.Normalize%2A> y recuperar el antecesor más cercano que se encuentra en la vista de contenido.  
  
<a name="Other_Ways_to_Retrieve_an_Element"></a>
## <a name="other-ways-to-retrieve-an-element"></a>Otras maneras de recuperar un elemento  
 Además de las búsquedas y la navegación, puede recuperar un elemento <xref:System.Windows.Automation.AutomationElement> de las maneras siguientes.  
  
### <a name="from-an-event"></a>Desde un evento  
 Cuando la aplicación recibe un evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , el objeto de origen que se pasa al controlador de eventos es un elemento <xref:System.Windows.Automation.AutomationElement>. Por ejemplo, si se ha suscrito a eventos de cambio de foco, el origen que se pasó a su <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> es el elemento que recibió el foco.  
  
 Para obtener más información, consulta [Subscribe to UI Automation Events](subscribe-to-ui-automation-events.md).  
  
### <a name="from-a-point"></a>Desde un punto  
 Si tiene coordenadas de pantalla (por ejemplo, una posición del cursor), puede recuperar un elemento <xref:System.Windows.Automation.AutomationElement> con el método estático <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> .  
  
### <a name="from-a-window-handle"></a>Desde un identificador de ventana  
 Para recuperar un elemento <xref:System.Windows.Automation.AutomationElement> desde un HWND, use el método estático <xref:System.Windows.Automation.AutomationElement.FromHandle%2A> .  
  
### <a name="from-the-focused-control"></a>Desde el control con el foco  
 Puede recuperar un elemento <xref:System.Windows.Automation.AutomationElement> que representa el control con el foco desde la propiedad estática <xref:System.Windows.Automation.AutomationElement.FocusedElement%2A> .  
  
## <a name="see-also"></a>Vea también

- [Buscar un elemento de UI Automation basándose en una condición de propiedad](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Navegar entre elementos de UI Automation con TreeWalker](navigate-among-ui-automation-elements-with-treewalker.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
