---
title: Acceso a objetos incrustados mediante la UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 05f9359aa055019b517abb1b7c86ca386d630e41
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513977"
---
# <a name="access-embedded-objects-using-ui-automation"></a>Acceso a objetos incrustados mediante la UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo puede utilizarse [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para exponer objetos incrustados en el contenido de un control de texto.  
  
> [!NOTE]
>  Los objetos incrustados pueden incluir imágenes, hipervínculos, botones, tablas o controles ActiveX.  
  
 Los objetos incrustados se consideran elementos secundarios del proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Esto permite que se puedan exponer mediante la misma estructura de árbol de Automatización de la interfaz de usuario que todos los demás elementos de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] . La funcionalidad, a su vez, se expone a través de los patrones de control que normalmente requiere el tipo de control de los objetos incrustados (por ejemplo, como los hipervínculos están basados en texto, admitirán <xref:System.Windows.Automation.TextPattern>).  
  
 ![Objetos incrustados en un contenedor de texto. ](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")  
Un ejemplo de documento con contenido textual, ("Sabía que?" ...) y dos objetos incrustados (una imagen de una ballena y un hipervínculo de texto), utilizados como destino para los ejemplos de código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo recuperar una colección de objetos incrustados desde un proveedor de texto de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Para el documento de ejemplo que se proporciona en la introducción, se devolverían dos objetos (un elemento de imagen y un elemento de texto).  
  
> [!NOTE]
>  El elemento de imagen debería tener texto intrínseco asociado a él que describa la imagen, normalmente en su <xref:System.Windows.Automation.AutomationElement.NameProperty> (por ejemplo, "Una ballena azul."). Sin embargo, cuando se obtiene un intervalo de texto que abarca el objeto de imagen, ni la imagen ni el texto descriptivo se devuelve en la secuencia de texto.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo obtener un intervalo de texto de un objeto incrustado dentro de un proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . El intervalo de texto recuperado es un intervalo vacío donde el extremo inicial se sitúa después de "... ocean.(space)" y el extremo final precede el punto final "." que representa el hipervínculo incrustado (como se muestra en la imagen que se incluye en la introducción). Aunque se trata de un intervalo vacío, no se considera un intervalo degenerado porque tiene una extensión distinta de cero.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.TextPattern> puede recuperar un objeto incrustado basado en texto como un hipervínculo; sin embargo, un elemento <xref:System.Windows.Automation.TextPattern> secundario deberá obtenerse a partir del objeto incrustado para exponer toda su funcionalidad.  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextPattern en Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Patrones de control de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Adición de contenido a un cuadro de texto mediante Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
