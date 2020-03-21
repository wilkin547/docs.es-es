---
title: Implementar el patrón de control Dock de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: b1213791609245209fa37e3cdcb0876c963bfeb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180206"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a>Implementar el patrón de control Dock de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IDockProvider>y se incluye información sobre propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.DockPattern> se utiliza para exponer las propiedades de acoplamiento de un control dentro de un contenedor de acoplamiento. Un contenedor de acoplamiento es un control que permite organizar elementos secundarios horizontal y verticalmente, relacionados entre sí. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
 ![Acoplar contenedor con dos secundarios acoplados.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")  
Ejemplo de acoplamiento de Visual Studio donde la ventana "Vista de clases" es DockPosition.Right y la ventana "Lista de errores" es DockPosition.Bottom  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Dock, tenga en cuenta las siguientes directrices y convenciones:  
  
- <xref:System.Windows.Automation.Provider.IDockProvider> no expone propiedades del contenedor de acoplamiento ni propiedades de controles que estén acoplados adyacentes al control actual dentro del contenedor de acoplamiento.  
  
- Los controles se acoplan de forma relativa entre ellos, según su valor actual de orden Z; cuanto mayor es su ubicación de orden Z, más lejos se colocan del borde especificado del contenedor de acoplamiento.  
  
- Si se cambia el tamaño del contenedor de acoplamiento, los controles acoplados dentro del contenedor cambiarán de posición y se alinearán con el mismo borde en el que estaban originalmente acoplados. Los controles acoplados también cambiarán de tamaño para rellenar el espacio dentro del contenedor según el comportamiento de acoplamiento de sus elementos <xref:System.Windows.Automation.DockPosition>. Por ejemplo, si se especifica <xref:System.Windows.Automation.DockPosition.Top> , los lados izquierdo y derecho del control se expandirán para rellenar el espacio disponible. Si se especifica <xref:System.Windows.Automation.DockPosition.Fill> , los cuatro lados del control se expandirán para rellenar el espacio disponible.  
  
- En un sistema de varios monitores, los controles se deben acoplar en el lado izquierdo o derecho del monitor actual. Si no es posible, deben acoplarse en el lado izquierdo del monitor que se encuentre más a la izquierda o en el lado derecho del monitor que se encuentre más a la derecha.  
  
<a name="Required_Members_for_IDockProvider"></a>
## <a name="required-members-for-idockprovider"></a>Miembros requeridos para IDockProvider  
 Se requieren los métodos y propiedades siguientes para implementar la interfaz de IDockProvider.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|Método|None|  
  
 Este patrón de control no tiene eventos asociados.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> - Cuando un control no puede ejecutar el estilo de acoplamiento solicitado.|  
  
## <a name="see-also"></a>Consulte también

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
