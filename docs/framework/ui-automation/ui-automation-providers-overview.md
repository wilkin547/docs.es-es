---
title: Información general sobre proveedores de UI Automation
description: Vea información general de los proveedores de automatización de la interfaz de usuario, que permiten a los controles comunicarse con aplicaciones cliente de UI Automation. Revise los tipos de proveedor y los conceptos de proveedor.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 08b6a199a98fb22f197ca0cf8a0268e5439aaf41
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163254"
---
# <a name="ui-automation-providers-overview"></a>Información general sobre proveedores de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Los proveedores de automatización de la interfaz de usuario permiten a los controles comunicarse con aplicaciones de cliente de automatización de la interfaz de usuario. En general, cada control u otro elemento distinto de un [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] está representado por un proveedor. El proveedor expone información sobre el elemento y, opcionalmente, implementa patrones de control que permiten a la aplicación cliente interactuar con el control.  
  
 Las aplicaciones cliente no suelen tener que trabajar directamente con proveedores. La mayoría de los controles estándar de las aplicaciones que utilizan Win32, Windows Forms o [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] marcos de trabajo se exponen automáticamente al [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sistema. Las aplicaciones que implementan controles personalizados también pueden implementar proveedores [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para esos controles y las aplicaciones cliente no tienen que realizar ningún paso especial para obtener acceso a ellos.  
  
 En este tema se proporciona información general sobre cómo los desarrolladores de controles implementan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proveedores, especialmente para los controles de Windows Forms y las ventanas de Win32.  
  
<a name="Types_of_Providers"></a>
## <a name="types-of-providers"></a>Tipos de proveedores  
 Los proveedores de automatización de la interfaz de usuario se dividen en dos categorías: proveedores del lado cliente y proveedores del lado servidor.  
  
### <a name="client-side-providers"></a>Proveedores del lado cliente  
 Los proveedores de cliente se implementan por los clientes de automatización de la interfaz de usuario para comunicarse con una aplicación que no admite, o no admite por completo, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Los proveedores del lado cliente suelen comunicarse con el servidor a través del límite del proceso mediante el envío y la recepción de mensajes de Windows.  
  
 Dado que los proveedores de automatización de la interfaz de usuario para los controles en Win32, Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] aplicaciones se proporcionan como parte del sistema operativo, las aplicaciones cliente rara vez tienen que implementar sus propios proveedores y esta información general no los cubre más.  
  
### <a name="server-side-providers"></a>Proveedores del lado servidor  
 Los proveedores del lado servidor se implementan mediante controles personalizados o aplicaciones que se basan en un marco de interfaz de usuario distinto de Win32, Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .  
  
 Los proveedores del lado servidor se comunican con aplicaciones cliente a través del límite de proceso al exponer interfaces al sistema principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , que a su vez atiende solicitudes de los clientes.  
  
<a name="AutomationProviderConcepts"></a>
## <a name="ui-automation-provider-concepts"></a>Conceptos del proveedor de la automatización de la interfaz de usuario  
 En esta sección se ofrecen breves explicaciones de algunos de los conceptos clave que debe entender para implementar proveedores de automatización de la interfaz de usuario.  
  
### <a name="elements"></a>Elementos  
 Los elementos[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] son partes de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] que son visibles para los clientes de la automatización de la interfaz de usuario. Entre los ejemplos se incluyen ventanas de aplicación, paneles, botones, información sobre herramientas, cuadros de lista y elementos de lista.  
  
### <a name="navigation"></a>Navegación  
 Los elementos[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se exponen a  clientes como un árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] construye el árbol navegando de un elemento a otro. Los proveedores habilitan la navegación para cada elemento y cada uno de ellos puede señalar a un elemento primario, elementos del mismo nivel y elementos secundarios.  
  
 Para más información sobre la vista del cliente del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Vistas  
 Un cliente puede ver el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] en tres vistas principales, como se muestra en la tabla siguiente.  
  
|||  
|-|-|  
|Vista sin formato|Contiene todos los elementos.|  
|Vista de control|Contiene elementos que son controles.|  
|Vista de contenido|Contiene elementos que tienen contenido.|  
  
 Para más información sobre vistas del cliente del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 Es responsabilidad de la implementación del proveedor definir un elemento como un elemento de contenido o un elemento de control. Los elementos de control pueden o no ser elementos de contenido, pero todos los elementos de contenido son elementos de control.  
  
### <a name="frameworks"></a>Marcos  
 Un marco de trabajo es un componente que administra controles secundarios, pruebas de aciertos y representación en un área de la pantalla. Por ejemplo, una ventana de Win32, que a menudo se conoce como HWND, puede actuar como un marco de trabajo que contiene varios [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementos como una barra de menús, una barra de estado y botones.  
  
 Los controles de contenedor de Win32 como cuadros de lista y vistas de árbol se consideran marcos de trabajo, porque contienen su propio código para representar elementos secundarios y realizar pruebas de aciertos en ellos. Por el contrario, un cuadro de lista [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] no es un marco de trabajo, porque la representación y las pruebas de aciertos se controlan mediante la ventana que lo contiene [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .  
  
 La [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] de una aplicación se puede componer de diferentes marcos de trabajo. Por ejemplo, una ventana de aplicación HWND podría contener HTML dinámico (DHTML) que a su vez contiene un componente como un cuadro combinado en un HWND.  
  
### <a name="fragments"></a>Fragments  
 Un fragmento es un subárbol completo de elementos de un marco de trabajo determinado. El elemento del nodo raíz del subárbol se denomina raíz del fragmento. Una raíz de fragmento no tiene un elemento primario, pero se hospeda en otro marco de trabajo, normalmente una ventana Win32 (HWND).  
  
### <a name="hosts"></a>Hosts  
 El nodo raíz de cada fragmento se debe hospedar en un elemento, normalmente una ventana Win32 (HWND). La excepción es el escritorio, que no se hospeda en ningún otro elemento. El host de un control personalizado es el HWND del propio control, no la ventana de la aplicación o cualquier otra ventana que pueda contener grupos de controles de nivel superior.  
  
 El host de un fragmento desempeña un papel importante en el suministro de servicios [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Permite la navegación a la raíz del fragmento y ofrece algunas propiedades predeterminadas para que el proveedor personalizado no tenga que implementarlas.  
  
## <a name="see-also"></a>Vea también

- [Implementación del proveedor de UI Automation en el servidor](server-side-ui-automation-provider-implementation.md)
