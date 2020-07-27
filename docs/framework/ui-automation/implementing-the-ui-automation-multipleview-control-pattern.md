---
title: Implementación del patrón de control MultipleView de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control MultipleView en la automatización de la interfaz de usuario. Consulte los miembros necesarios para la interfaz IMultipleViewProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 0d65d57637891fcb1307f5ee83a417941ff323fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168222"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a>Implementación del patrón de control MultipleView de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, incluida la información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.MultipleViewPattern> se usa para admitir controles que ofrecen y pueden cambiar entre varias representaciones del mismo conjunto de información o controles secundarios.  
  
 Algunos ejemplos de controles que pueden presentar varias vistas son la vista de lista (que puede mostrar su contenido como miniaturas, mosaicos, iconos o detalles), gráficos de Microsoft Excel (circular, línea, barra, valor de celda con una fórmula), documentos de Microsoft Word (normal, diseño web, diseño de impresión, diseño de lectura, esquema), calendario de Microsoft Outlook (año, mes, semana, día) y máscaras de Media Player de Microsoft Windows. Las vistas admitidas las determina el desarrollador del control y son específicas de cada control.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Multiple View, tenga en cuenta las siguientes directrices y convenciones:  
  
- <xref:System.Windows.Automation.Provider.IMultipleViewProvider> también se debe implementar en un contenedor que administre la vista actual si es diferente de un control que ofrece la vista actual. Por ejemplo, el Explorador de Windows contiene un control de lista para el contenido de la carpeta actual, mientras que la vista del control se administra desde la aplicación del Explorador de Windows.  
  
- No se considera que un control que puede ordenar su contenido admita varias vistas.  
  
- La colección de vistas debe ser idéntica en todas las instancias.  
  
- Los nombres de vista deben ser adecuados para su usarlo en texto a voz, Braille y otras aplicaciones de lenguaje natural.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a>Miembros requeridos para IMultipleViewProvider  
 Para implementar IMultipleViewProvider, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Método|None|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Método|None|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Método|None|  
  
 No hay ningún evento asociado a este patrón de control.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Excepciones  
 Los proveedores debe generar las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Cuando se llama a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parámetro que no es miembro de la colección de vistas compatible.|  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
