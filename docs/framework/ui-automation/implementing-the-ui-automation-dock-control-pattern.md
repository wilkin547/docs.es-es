---
title: "Implementing the UI Automation Dock Control Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control patterns, dock"
  - "dock control pattern"
  - "UI Automation, dock control pattern"
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
caps.latest.revision: 23
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 23
---
# Implementing the UI Automation Dock Control Pattern
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IDockProvider> y se incluye información sobre propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.DockPattern> se utiliza para exponer las propiedades de acoplamiento de un control dentro de un contenedor de acoplamiento. Un contenedor de acoplamiento es un control que permite organizar elementos secundarios horizontal y verticalmente, relacionados entre sí. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
 ![Acoplar contenedor con dos secundarios acoplados.](../../../docs/framework/ui-automation/media/uia-dockpattern-dockingexample.PNG "UIA\_DockPattern\_DockingExample")  
Ejemplo de acoplamiento de Visual Studio donde la ventana "Vista de clases" es DockPosition.Right y la ventana "Lista de errores" es DockPosition.Bottom  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Directrices y convenciones de implementación  
 Al implementar el patrón de control Dock, tenga en cuenta las siguientes directrices y convenciones:  
  
-   <xref:System.Windows.Automation.Provider.IDockProvider> no expone propiedades del contenedor de acoplamiento ni propiedades de controles que estén acoplados adyacentes al control actual dentro del contenedor de acoplamiento.  
  
-   Los controles se acoplan de forma relativa entre ellos, según su valor actual de orden Z; cuanto mayor es su ubicación de orden Z, más lejos se colocan del borde especificado del contenedor de acoplamiento.  
  
-   Si se cambia el tamaño del contenedor de acoplamiento, los controles acoplados dentro del contenedor cambiarán de posición y se alinearán con el mismo borde en el que estaban originalmente acoplados. Los controles acoplados también cambiarán de tamaño para rellenar el espacio dentro del contenedor según el comportamiento de acoplamiento de sus elementos <xref:System.Windows.Automation.DockPosition>. Por ejemplo, si se especifica <xref:System.Windows.Automation.DockPosition>, los lados izquierdo y derecho del control se expandirán para rellenar el espacio disponible. Si se especifica <xref:System.Windows.Automation.DockPosition>, los cuatro lados del control se expandirán para rellenar el espacio disponible.  
  
-   En un sistema de varios monitores, los controles se deben acoplar en el lado izquierdo o derecho del monitor actual. Si no es posible, deben acoplarse en el lado izquierdo del monitor que se encuentre más a la izquierda o en el lado derecho del monitor que se encuentre más a la derecha.  
  
<a name="Required_Members_for_IDockProvider"></a>   
## Miembros requeridos para IDockProvider  
 Se requieren los métodos y propiedades siguientes para implementar la interfaz de IDockProvider.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|-------------------------|---------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|Método|Ninguna|  
  
 Este patrón de control no tiene eventos asociados.  
  
<a name="Exceptions"></a>   
## Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|-----------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> -   Cuando un control no puede ejecutar el estilo de acoplamiento solicitado.|  
  
## Vea también  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)