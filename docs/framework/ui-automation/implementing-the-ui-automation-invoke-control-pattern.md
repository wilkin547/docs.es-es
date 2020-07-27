---
title: Implementar el patrón de control Invoke de UI Automation
description: Lea las directrices y convenciones para implementar el patrón de control Invoke en la automatización de la interfaz de usuario. Consulte los miembros necesarios para la interfaz IInvokeProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
ms.openlocfilehash: b464b3ab5cd2b0789798f8b865b946c5eae017eb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166169"
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a>Implementar el patrón de control Invoke de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>, incluida la información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.

El patrón de control <xref:System.Windows.Automation.InvokePattern> se utiliza para admitir controles que no mantienen el estado cuando se activan, sino que inician o realizan una única acción inequívoca. Los controles que mantienen el estado, como las casillas y los botones de radio, deben implementar en su lugar <xref:System.Windows.Automation.Provider.IToggleProvider> y <xref:System.Windows.Automation.Provider.ISelectionItemProvider> , respectivamente. Para obtener ejemplos de controles que implementan el patrón de control Invoke, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación

Al implementar el patrón de control Invoke, tenga en cuenta las siguientes directrices y convenciones:

- Los controles implementan <xref:System.Windows.Automation.Provider.IInvokeProvider> si el mismo comportamiento no se expone a través de otro proveedor de patrón de control. Por ejemplo, si el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A> de un control realiza la misma acción que los métodos <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> , el control no debe implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>.

- Generalmente, la invocación de un control se realiza con un clic, un doble clic, presionando la tecla ENTRAR, usando un método abreviado de teclado predefinido o alguna combinación alternativa de pulsaciones de teclas.

- Se genera<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> en un control que se ha activado (como respuesta a un control que lleva a cabo su acción asociada). Si es posible, se debe generar el evento después de que el control haya completado la acción y haya hecho la devolución sin bloquearse. El evento Invoked debe generarse antes de atender la solicitud Invoke en los escenarios siguientes:

  - No es posible ni práctico esperar hasta que se complete la acción.

  - La acción requiere la interacción del usuario.

  - La acción requiere mucho tiempo y provocará que el cliente que llama se bloquee durante un tiempo considerable.

- Si la invocación del control tiene efectos secundarios significativos, esos efectos secundarios se deben exponer a través de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> . Por ejemplo, aunque <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> no se asocie a la selección, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> puede provocar que se seleccione otro control.

- Normalmente, los efectos de mantener el puntero (o pasar el mouse por encima) no constituyen un evento Invoked. Sin embargo, los controles que realizan una acción (en lugar de producir un efecto visual) según el estado del efecto de mantener el puntero deben admitir el patrón de control <xref:System.Windows.Automation.InvokePattern> .

> [!NOTE]
> Esta implementación se considera un problema de accesibilidad si el control solo se puede invocar como resultado de un efecto secundario relacionado con el mouse.

- La invocación de un control es diferente de la selección de un elemento. No obstante, dependiendo del control, su invocación puede provocar que el elemento se seleccione como un efecto secundario. Por ejemplo, la invocación de un elemento de lista de documentos de Microsoft Word en la carpeta Mis documentos selecciona el elemento y abre el documento.

- Un elemento puede desaparecer del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] inmediatamente después de que se invoque. La solicitud de información del elemento que proporciona la devolución de llamada de evento puede producir un error como resultado. La solución recomendada es la captura previa de la información almacenada en caché.

- Los controles pueden implementar varios patrones de control. Por ejemplo, el control color de relleno de la barra de herramientas de Microsoft Excel implementa los <xref:System.Windows.Automation.InvokePattern> <xref:System.Windows.Automation.ExpandCollapsePattern> patrones de control y. <xref:System.Windows.Automation.ExpandCollapsePattern> expone el menú y el elemento <xref:System.Windows.Automation.InvokePattern> rellena la selección activa con el color elegido.

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iinvokeprovider"></a>Miembros requeridos para IInvokeProvider

Para implementar <xref:System.Windows.Automation.Provider.IInvokeProvider>, se requieren las siguientes propiedades y métodos.

|Miembros requeridos|Tipo de miembro|Notas|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|method|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> es una llamada asincrónica y debe volver inmediatamente sin bloquearse.<br /><br /> Este comportamiento es especialmente importante para los controles que, directa o indirectamente, inician un cuadro de diálogo modal cuando se invocan. Cualquier cliente de Automatización de la interfaz de usuario que haya provocado que el evento permanezca bloqueado hasta que se cierre el cuadro de diálogo modal.|

<a name="Exceptions"></a>

## <a name="exceptions"></a>Excepciones

Los proveedores deben producir las siguientes excepciones.

|Tipo de excepción|Condición|
|--------------------|---------------|
|<xref:System.Windows.Automation.ElementNotEnabledException>|Si el control no está habilitado.|

## <a name="see-also"></a>Vea también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Llamar a un control utilizando la UI Automation](invoke-a-control-using-ui-automation.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
