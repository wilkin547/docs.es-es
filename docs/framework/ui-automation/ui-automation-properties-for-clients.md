---
title: Propiedades de UI Automation para clientes
description: Lea información general sobre las propiedades de automatización de la interfaz de usuario a medida que se exponen a las aplicaciones cliente de UI Automation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, UI Automation clients
- UI Automation, client properties
ms.assetid: 255905af-0b17-485c-93d4-8a2db2a6524b
ms.openlocfilehash: f86351f430e2d133a31cf6af81b41789ba444078
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279134"
---
# <a name="ui-automation-properties-for-clients"></a>Propiedades de UI Automation para clientes

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Esta introducción presenta las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tal como se exponen en las aplicaciones cliente de Automatización de la interfaz de usuario.  
  
 Las propiedades de los objetos <xref:System.Windows.Automation.AutomationElement> contienen información sobre elementos de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , normalmente controles. Las propiedades de un elemento <xref:System.Windows.Automation.AutomationElement> son genéricas; es decir, no son específicas de un tipo de control. Muchas de estas propiedades se exponen en la estructura <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation> .  
  
 Los patrones de control también tienen propiedades. Las propiedades de los patrones de control son específicas para el modelo. Por ejemplo, <xref:System.Windows.Automation.ScrollPattern> tiene propiedades que permiten a una aplicación cliente detectar si una ventana es desplazable horizontal o verticalmente, y cuáles son los tamaños de la vista actual y las posiciones de desplazamiento. Los patrones de control exponen todas sus propiedades a través de una estructura; por ejemplo, <xref:System.Windows.Automation.ScrollPattern.ScrollPatternInformation>.  
  
 Las propiedades de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] son de solo lectura. Para establecer las propiedades de un control, debe utilizar los métodos del patrón de control adecuado. Por ejemplo, utilice <xref:System.Windows.Automation.ScrollPattern.Scroll%2A> para cambiar los valores de posición de una ventana desplazable.  
  
 Para mejorar el rendimiento, los valores de propiedad de los controles y los patrones de control pueden almacenarse en caché cuando se recuperan objetos <xref:System.Windows.Automation.AutomationElement> . Para obtener más información, vea [almacenamiento en caché en los clientes de UI Automation](caching-in-ui-automation-clients.md).  
  
## <a name="property-ids"></a>Identificadores de propiedad  

 Los identificadores de propiedad (ID) son valores constantes únicos que se encapsulan en <xref:System.Windows.Automation.AutomationProperty> objetos. Las aplicaciones cliente de automatización de la interfaz de usuario obtienen estos identificadores de la <xref:System.Windows.Automation.AutomationElement> clase o de la clase de patrón de control apropiada, como <xref:System.Windows.Automation.ScrollPattern> . Los proveedores de Automatización de la interfaz de usuario los obtienen de <xref:System.Windows.Automation.AutomationElementIdentifiers> o de una de las clases de identificadores de patrón de control, como <xref:System.Windows.Automation.ScrollPatternIdentifiers>.  
  
 Los proveedores usan el valor numérico <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> de un elemento <xref:System.Windows.Automation.AutomationProperty> para identificar las propiedades que se consultan en el método <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A?displayProperty=nameWithType> . En general, las aplicaciones cliente no necesitan examinar el elemento <xref:System.Windows.Automation.AutomationIdentifier.Id%2A>. <xref:System.Windows.Automation.AutomationIdentifier.ProgrammaticName%2A> se utiliza únicamente con fines de depuración y diagnóstico.  
  
## <a name="property-conditions"></a>Condiciones de propiedad  

 Los identificadores de propiedad se utilizan en la creación de <xref:System.Windows.Automation.PropertyCondition> objetos que se usan para buscar <xref:System.Windows.Automation.AutomationElement> objetos. Por ejemplo, podría querer buscar un elemento <xref:System.Windows.Automation.AutomationElement> que tenga un nombre determinado o todos los controles que están habilitados. Cada <xref:System.Windows.Automation.PropertyCondition> especifica un identificador <xref:System.Windows.Automation.AutomationProperty> y el valor con el que debe coincidir la propiedad.  
  
 Para más información, consulte los temas de referencia siguientes:  
  
- <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.FindAll%2A>  
  
- <xref:System.Windows.Automation.TreeWalker.Condition%2A>  
  
## <a name="retrieving-properties"></a>Recuperación de propiedades  

 Algunas propiedades de <xref:System.Windows.Automation.AutomationElement> y todas las propiedades de una clase de patrón de control se exponen como propiedades anidadas de las propiedades `Current` o `Cached` del objeto de patrón de control <xref:System.Windows.Automation.AutomationElement> .  
  
 Además, cualquier propiedad de patrón de control o <xref:System.Windows.Automation.AutomationElement> , incluida una propiedad que no esté disponible en la estructura <xref:System.Windows.Automation.AutomationElement.Cached%2A> o <xref:System.Windows.Automation.AutomationElement.Current%2A> , se puede recuperar con uno de los métodos siguientes:  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>  
  
 Estos métodos ofrecen un rendimiento ligeramente superior así como acceso a la gama completa de propiedades.  
  
 En el ejemplo de código siguiente se muestran las dos maneras de recuperar una propiedad en un elemento <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#121](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#121)]
 [!code-vb[UIAClient_snip#121](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#121)]  
  
 Para recuperar propiedades de los patrones de control que admite el elemento <xref:System.Windows.Automation.AutomationElement>, no es necesario recuperar el objeto de patrón de control. Basta con pasar uno de los identificadores de propiedad de patrón al método.  
  
 En el ejemplo de código siguiente se muestran las dos maneras de recuperar una propiedad en un patrón de control.  
  
 [!code-csharp[UIAClient_snip#122](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#122)]
 [!code-vb[UIAClient_snip#122](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#122)]  
  
 Los métodos `Get` devuelven un elemento <xref:System.Object>. La aplicación debe convertir el objeto devuelto al tipo apropiado antes de utilizar el valor.  
  
## <a name="default-property-values"></a>Valores de propiedad predeterminados  

 Si un proveedor de Automatización de la interfaz de usuario no implementa una propiedad, el sistema de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es capaz de facilitar un valor predeterminado. Por ejemplo, si el proveedor de un control no admite la propiedad identificada por <xref:System.Windows.Automation.AutomationElement.HelpTextProperty>, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devuelve una cadena vacía. De forma similar, si el proveedor no admite la propiedad identificada por <xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devuelve `false`.  
  
 Puede cambiar este comportamiento mediante las sobrecargas del método <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> . Cuando se especifica `true` como el segundo parámetro, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no devuelve un valor predeterminado, sino que en su lugar devuelve el valor especial <xref:System.Windows.Automation.AutomationElement.NotSupported>.  
  
 En el ejemplo de código siguiente se intenta recuperar una propiedad de un elemento y, si no se admite la propiedad, se utiliza un valor definido por la aplicación en su lugar.  
  
 [!code-csharp[UIAClient_snip#123](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#123)]
 [!code-vb[UIAClient_snip#123](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#123)]  
  
 Para detectar las propiedades que admite un elemento, utilice <xref:System.Windows.Automation.AutomationElement.GetSupportedProperties%2A>. Esto devuelve una matriz de identificadores <xref:System.Windows.Automation.AutomationProperty> .  
  
## <a name="property-changed-events"></a>Eventos de cambio de propiedades  

 Cuando el valor de una propiedad de un elemento <xref:System.Windows.Automation.AutomationElement> o un patrón de control cambia, se produce un evento. Una aplicación puede suscribirse a dichos eventos mediante una llamada a <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>, proporcionando una matriz de identificadores <xref:System.Windows.Automation.AutomationProperty> como el último parámetro para especificar las propiedades de interés.  
  
 En el elemento <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>, puede identificar la propiedad que ha cambiado si comprueba el miembro <xref:System.Windows.Automation.AutomationPropertyChangedEventArgs.Property%2A> de los argumentos del evento. Los argumentos también contienen los valores antiguos y nuevos de la propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que ha cambiado. Estos valores son del tipo <xref:System.Object> y se deben convertir al tipo correcto antes de utilizarse.  
  
## <a name="additional-automationelement-properties"></a>Propiedades adicionales de AutomationElement  

 Además de las estructuras de propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y <xref:System.Windows.Automation.AutomationElement.Cached%2A> , <xref:System.Windows.Automation.AutomationElement> tiene las propiedades siguientes, que se recuperan mediante descriptores de acceso de propiedades simples.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Automation.AutomationElement.CachedChildren%2A>|Una colección de objetos de elementos secundarios <xref:System.Windows.Automation.AutomationElement> que están en la caché.|  
|<xref:System.Windows.Automation.AutomationElement.CachedParent%2A>|Un objeto primario <xref:System.Windows.Automation.AutomationElement> que está en la caché.|  
|<xref:System.Windows.Automation.AutomationElement.FocusedElement%2A>|(Propiedad estática) El elemento <xref:System.Windows.Automation.AutomationElement> que tiene el foco de entrada.|  
|<xref:System.Windows.Automation.AutomationElement.RootElement%2A>|(Propiedad estática) El elemento <xref:System.Windows.Automation.AutomationElement>raíz.|  
  
## <a name="see-also"></a>Vea también

- [Almacenar en caché en los clientes de automatización de la interfaz de usuario](caching-in-ui-automation-clients.md)
- [Implementación del proveedor de UI Automation en el servidor](server-side-ui-automation-provider-implementation.md)
- [Suscribirse a eventos de UI Automation](subscribe-to-ui-automation-events.md)
