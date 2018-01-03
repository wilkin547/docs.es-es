---
title: "Información general sobre UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, overview
- user interface, see UI
- accessibility, UI automation
ms.assetid: 65847654-9994-4a9e-b36d-2dd5d998770b
caps.latest.revision: "35"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d86c70ec4421bc716b12044bac30f8f925c375f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-overview"></a>Información general sobre UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] es el nuevo marco de trabajo de accesibilidad para [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)], disponible en todos los sistemas operativos que admiten [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece acceso mediante programación a la mayoría de los elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] del escritorio y permite productos de tecnología de asistencia como lectores de pantalla para ofrecer información sobre [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] a los usuarios finales y manipular [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] por otros medios distintos de la entrada estándar. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] también permite que scripts de pruebas automatizadas interactúen con [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]no permite la comunicación entre procesos iniciados por usuarios diferentes mediante el **de identificación de** comando.  
  
 Las aplicaciones cliente de la automatización de la interfaz de usuario se pueden escribir con la certeza de que funcionarán en varios marcos de trabajo. El núcleo de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] enmascara las diferencias entre los marcos de trabajo que subyacen a distintas partes de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Por ejemplo, la propiedad `Content` de un botón [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , la propiedad `Caption` de un botón [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] y la propiedad `ALT` de una imagen HTML se asignan a una sola propiedad, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>, en la vista [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece funcionalidad completa en [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)]y [!INCLUDE[TLA2#tla_winnetsvrfam](../../../includes/tla2sharptla-winnetsvrfam-md.md)].  
  
 Los proveedores de la automatización de la interfaz de usuario ofrecen algo de compatibilidad con las aplicaciones cliente [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] , a través de un servicio de puente integrado.  
  
<a name="Providers_and_Clients"></a>   
## <a name="providers-and-clients"></a>Proveedores y clientes  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tiene cuatro componentes principales, como se muestra en la tabla siguiente.  
  
|Componente|Descripción|  
|---------------|-----------------|  
|Proveedor [!INCLUDE[TLA#tla_api](../../../includes/tlasharptla-api-md.md)] (UIAutomationProvider.dll y UIAutomationTypes.dll)|Conjunto de definiciones de interfaz que se implementan por proveedores de la automatización de la interfaz de usuario, que ofrecen información sobre los objetos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] y que responden a la entrada mediante programación.|  
|API de cliente (UIAutomationClient.dll y UIAutomationTypes.dll)|Conjunto de tipos de código administrado que permite a las aplicaciones cliente de la automatización de la interfaz de usuario obtener información sobre la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] y enviar la entrada a controles.|  
|UiAutomationCore.dll|El código subyacente (a veces denominado el núcleo de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ) que controla la comunicación entre los proveedores y los clientes.|  
|UIAutomationClientsideProviders.dll|Un conjunto de proveedores de automatización de la interfaz de usuario para controles heredados estándar. ([!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] controles tienen compatibilidad nativa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].) Esta compatibilidad está disponible automáticamente para las aplicaciones cliente.|  
  
 Desde la perspectiva del desarrollador de software, hay dos formas de usar [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: crear compatibilidad con controles personalizados (mediante la API de proveedor) y creando aplicaciones que usan el núcleo de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para comunicarse con elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] (mediante la API del cliente). En función de su enfoque, debe hacer referencia a diferentes partes de la documentación. Puede obtener más información sobre los conceptos y adquirir conocimientos prácticos en las secciones siguientes.  
  
|Sección|Materia|Audiencia|  
|-------------|--------------------|--------------|  
|[Fundamentos de UI Automation](../../../docs/framework/ui-automation/index.md) (esta sección)|Amplias introducciones a los conceptos.|Todos.|  
|[Proveedores de Automatización de la interfaz de usuario para código administrado](../../../docs/framework/ui-automation/ui-automation-providers-for-managed-code.md)|Información general y temas de procedimientos que le ayudarán a usar la API del proveedor.|Desarrolladores de controles.|  
|[Clientes de Automatización de la interfaz de usuario para código administrado](../../../docs/framework/ui-automation/ui-automation-clients-for-managed-code.md)|Información general y temas de procedimientos que le ayudarán a usar la API del cliente.|Desarrolladores de aplicaciones de cliente.|  
|[Patrones de control de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)|Información sobre cómo sedeben implementar los patrones de control por los proveedores y qué funcionalidad está disponible para los clientes.|Todos.|  
|[Patrón de texto de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)|Información sobre cómo sedeben implementar el patrón de control Text por los proveedores y qué funcionalidad está disponible para los clientes.|Todos.|  
|[UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md)|Información sobre las propiedades y los patrones de control admitidos por diferentes tipos de control.|Todos.|  
  
 En la tabla siguiente se muestran espacios de nombres [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , archivos DLL que los contienen y el público que los usa.  
  
|Espacio de nombres|DLL a las que se hace referencia|Audiencia|  
|---------------|---------------------|--------------|  
|<xref:System.Windows.Automation>|UIAutomationClientUIAutomationTypes|Desarrolladores de cliente de automatización de la interfaz de usuario; se utiliza para buscar objetos <xref:System.Windows.Automation.AutomationElement> , registrarse para eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y trabajar con patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.Provider>|UIAutomationProviderUIAutomationTypes|Los desarrolladores de los proveedores de automatización de la interfaz de usuario para marcos de trabajo distintos de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Windows.Automation.Text>|UIAutomationClientUIAutomationTypes|Los desarrolladores de proveedores de la automatización de la interfaz de usuario para marcos de trabajo distintos de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]; se usan para implementar el patrón de control TextPattern.|  
|<xref:System.Windows.Automation.Peers>|PresentationFramework|Desarrolladores de los proveedores de la automatización de la interfaz de usuario para [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
  
<a name="UI_Automation_Model"></a>   
## <a name="ui-automation-model"></a>Modelo de la automatización de la interfaz de usuario  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] expone cada parte de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] a las aplicaciones cliente como un <xref:System.Windows.Automation.AutomationElement>. Los elementos se encuentran en una estructura de árbol, con el escritorio como el elemento raíz. Los clientes pueden filtrar la vista sin formato del árbol como una vista de control o una vista de contenido. Las aplicaciones también pueden crear vistas personalizadas.  
  
 Los objetos<xref:System.Windows.Automation.AutomationElement> exponen propiedades comunes de los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que representan. Una de estas propiedades es el tipo de control, que define su funcionalidad y aspecto básico como una única entidad reconocible: por ejemplo, un botón o una casilla.  
  
 Además, los elementos exponen los patrones de control que ofrecen propiedades específicas para sus tipos de control. Los patrones de control también exponen métodos que permiten a los clientes obtener más información sobre el elemento y ofrecer entrada.  
  
> [!NOTE]
>  No hay una correspondencia de uno a uno entre los tipos de control y los patrones de control. Un patrón de control puede ser compatible con varios tipos de control y un control puede admitir varios patrones de control, cada uno de los cuales expone diferentes aspectos de su comportamiento. Por ejemplo, un cuadro combinado tiene al menos dos patrones de control: uno que representa su capacidad para expandir y contraer, y otro que representa el mecanismo de selección. Para obtener información específica, vea [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] también ofrece información para las aplicaciones cliente a través de eventos. A diferencia de [!INCLUDE[TLA2#tla_winevents](../../../includes/tla2sharptla-winevents-md.md)], los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no se basan en un mecanismo de difusión. Los clientes[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se registran para notificaciones de evento específicas y pueden solicitar que se pase información de patrón de control y propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] específicas a sus controladores de eventos. Además, un evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] contiene una referencia al elemento que lo generó. Los proveedores pueden mejorar el rendimiento generando eventos de forma selectiva, dependiendo de si los clientes están escuchando.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el árbol de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Información general sobre las propiedades de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [Información general sobre eventos de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Información general sobre la seguridad de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-security-overview.md)
