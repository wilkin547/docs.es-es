---
title: Obtener detalles de atributos de texto diversos mediante UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: 9f2cba1f602cedf3a13bd909b4dc2f1a7b4ab972
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443124"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Obtener detalles de atributos de texto diversos mediante UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obtener detalles de atributos de texto de un intervalo de texto que abarca varios valores de atributo. Un intervalo de texto puede corresponder a la ubicación actual del símbolo de intercalación (o selección degenerada) dentro de un documento, una selección contigua de texto, una colección de selecciones de textos inconexos o todo el contenido textual de un documento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo obtener el valor <xref:System.Windows.Automation.TextPattern.FontNameAttribute> de un intervalo de texto donde <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> devuelve un objeto <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .  
  
[!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
[!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 El patrón de control <xref:System.Windows.Automation.TextPattern> , junto con la clase <xref:System.Windows.Automation.Text.TextPatternRange> , admite atributos de texto básicos, propiedades y métodos. Para la funcionalidad específica del control que no es compatible con <xref:System.Windows.Automation.TextPattern> ni <xref:System.Windows.Automation.Text.TextPatternRange>, la clase <xref:System.Windows.Automation.AutomationElement> ofrece métodos para que un cliente de Automatización de la interfaz de usuario acceda al modelo de objeto nativo correspondiente.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre TextPattern en Automatización de la interfaz de usuario](ui-automation-textpattern-overview.md)
- [Adición de contenido a un cuadro de texto mediante Automatización de la interfaz de usuario](add-content-to-a-text-box-using-ui-automation.md)
- [Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario](find-and-highlight-text-using-ui-automation.md)
- [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](ui-automation-control-patterns-overview.md)
- [UI Automation Control Patterns for Clients](ui-automation-control-patterns-for-clients.md)
- [Obtención de atributos de texto mediante Automatización de la interfaz de usuario](obtain-text-attributes-using-ui-automation.md)
