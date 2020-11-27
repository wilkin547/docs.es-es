---
title: Obtener detalles de atributos de texto diversos mediante UI Automation
description: Obtenga detalles de atributos de texto mixtos mediante las clases de automatización de la interfaz de usuario administrada en el espacio de nombres System. Windows. Automation de la API de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: ac6b212a8cb3f2f0cfa0d645aba2f0984ed8eb60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274652"
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

- [Información general sobre el modelo de texto de UI Automation](ui-automation-textpattern-overview.md)
- [Agregar contenido a un cuadro de texto utilizando la UI Automation](add-content-to-a-text-box-using-ui-automation.md)
- [Buscar y resaltar texto mediante UI Automation](find-and-highlight-text-using-ui-automation.md)
- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Obtener atributos de texto mediante UI Automation](obtain-text-attributes-using-ui-automation.md)
