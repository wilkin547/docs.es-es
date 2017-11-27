---
title: "Implementar el patrón de control Invoke de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
caps.latest.revision: "31"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: d42952328f70fec32b4a2cb58733785b3c1d97ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a>Implementar el patrón de control Invoke de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>y se incluye información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.InvokePattern> se utiliza para admitir controles que no mantienen el estado cuando se activan, sino que inician o realizan una única acción inequívoca. Los controles que mantienen el estado, como las casillas y los botones de radio, deben implementar en su lugar <xref:System.Windows.Automation.Provider.IToggleProvider> y <xref:System.Windows.Automation.Provider.ISelectionItemProvider> , respectivamente. Para obtener ejemplos de controles que implementan el patrón de control Invoke, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Invoke, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los controles implementan <xref:System.Windows.Automation.Provider.IInvokeProvider> si el mismo comportamiento no se expone a través de otro proveedor de patrón de control. Por ejemplo, si el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A> de un control realiza la misma acción que los métodos <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> , el control no debe implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>.  
  
-   Generalmente, la invocación de un control se realiza con un clic, un doble clic, presionando la tecla ENTRAR, usando un método abreviado de teclado predefinido o alguna combinación alternativa de pulsaciones de teclas.  
  
-   Se genera<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> en un control que se ha activado (como respuesta a un control que lleva a cabo su acción asociada). Si es posible, se debe generar el evento después de que el control haya completado la acción y haya hecho la devolución sin bloquearse. El evento Invoked debe generarse antes de atender la solicitud Invoke en los escenarios siguientes:  
  
    -   No es posible ni práctico esperar hasta que se complete la acción.  
  
    -   La acción requiere la interacción del usuario.  
  
    -   La acción requiere mucho tiempo y provocará que el cliente que llama se bloquee durante un tiempo considerable.  
  
-   Si la invocación del control tiene efectos secundarios significativos, esos efectos secundarios se deben exponer a través de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> . Por ejemplo, aunque <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> no se asocie a la selección, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> puede provocar que se seleccione otro control.  
  
-   Normalmente, los efectos de mantener el puntero (o pasar el mouse por encima) no constituyen un evento Invoked. Sin embargo, los controles que realizan una acción (en lugar de producir un efecto visual) según el estado del efecto de mantener el puntero deben admitir el patrón de control <xref:System.Windows.Automation.InvokePattern> .  
  
> [!NOTE]
>  Esta implementación se considera un problema de accesibilidad si el control solo se puede invocar como resultado de un efecto secundario relacionado con el mouse.  
  
-   La invocación de un control es diferente de la selección de un elemento. No obstante, dependiendo del control, su invocación puede provocar que el elemento se seleccione como un efecto secundario. Por ejemplo, la invocación de un elemento de lista de documentos [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] en la carpeta Mis documentos selecciona el elemento y abre el documento.  
  
-   Un elemento puede desaparecer del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] inmediatamente después de que se invoque. La solicitud de información del elemento que proporciona la devolución de llamada de evento puede producir un error como resultado. La solución recomendada es la captura previa de la información almacenada en caché.  
  
-   Los controles pueden implementar varios patrones de control. Por ejemplo, el control Fill Color de la barra de herramientas de [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] implementa los patrones de control <xref:System.Windows.Automation.InvokePattern> y <xref:System.Windows.Automation.ExpandCollapsePattern> . <xref:System.Windows.Automation.ExpandCollapsePattern> expone el menú y el elemento <xref:System.Windows.Automation.InvokePattern> rellena la selección activa con el color elegido.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iinvokeprovider"></a>Miembros requeridos para IInvokeProvider  
 Para implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|método|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> es una llamada asincrónica y debe volver inmediatamente sin bloquearse.<br /><br /> Este comportamiento es especialmente importante para los controles que, directa o indirectamente, inician un cuadro de diálogo modal cuando se invocan. Cualquier cliente de Automatización de la interfaz de usuario que haya provocado que el evento permanezca bloqueado hasta que se cierre el cuadro de diálogo modal.|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Si el control no está habilitado.|  
  
## <a name="see-also"></a>Vea también  
 [Información general del patrones de Control UI Automation](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Patrones de Control compatibles en un proveedor de UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Llamar a un Control utilizando la UI Automation](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [Información general sobre el árbol de automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Usar almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
