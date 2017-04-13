---
title: "Access Embedded Objects Using UI Automation | Microsoft Docs"
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
  - "embedded objects, accessing"
  - "accessing embedded objects"
  - "UI Automation, accessing embedded objects"
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: 17
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 17
---
# Access Embedded Objects Using UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo puede utilizarse [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para exponer objetos incrustados en el contenido de un control de texto.  
  
> [!NOTE]
>  Los objetos incrustados pueden incluir imágenes, hipervínculos, botones, tablas o controles ActiveX.  
  
 Los objetos incrustados se consideran elementos secundarios del proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Esto permite que se puedan exponer mediante la misma estructura de árbol de Automatización de la interfaz de usuario que todos los demás elementos de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]. La funcionalidad, a su vez, se expone a través de los patrones de control que normalmente requiere el tipo de control de los objetos incrustados \(por ejemplo, como los hipervínculos están basados en texto, admitirán <xref:System.Windows.Automation.TextPattern>\).  
  
 ![Objetos incrustados en un contenedor de texto.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA\_TextPattern\_EmbeddedObjects")  
Un documento de muestra con contenido textual, \("¿Sabía que?"…\) y dos objetos incrustados \(una imagen de una ballena y un hipervínculo de texto\), utilizados como destino para los ejemplos de código.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo recuperar una colección de objetos incrustados desde un proveedor de texto de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Para el documento de ejemplo que se proporciona en la introducción, se devolverían dos objetos \(un elemento de imagen y un elemento de texto\).  
  
> [!NOTE]
>  El elemento de imagen debería tener texto intrínseco asociado a él que describa la imagen, normalmente en su <xref:System.Windows.Automation.AutomationElement.NameProperty> \(por ejemplo, "Una ballena azul."\). Sin embargo, cuando se obtiene un intervalo de texto que abarca el objeto de imagen, ni la imagen ni el texto descriptivo se devuelve en la secuencia de texto.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo obtener un intervalo de texto de un objeto incrustado dentro de un proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. El intervalo de texto recuperado es un intervalo vacío donde el extremo inicial se sitúa después de "... ocean.\(space\)" y el extremo final precede el punto final "." que representa el hipervínculo incrustado \(como se muestra en la imagen que se incluye en la introducción\). Aunque se trata de un intervalo vacío, no se considera un intervalo degenerado porque tiene una extensión distinta de cero.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.TextPattern> puede recuperar un objeto incrustado basado en texto como un hipervínculo; sin embargo, un elemento <xref:System.Windows.Automation.TextPattern> secundario deberá obtenerse a partir del objeto incrustado para exponer toda su funcionalidad.  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## Vea también  
 [UI Automation TextPattern Overview](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)   
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Add Content to a Text Box Using UI Automation](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)   
 [Find and Highlight Text Using UI Automation](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)