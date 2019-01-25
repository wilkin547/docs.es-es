---
title: Procedimiento Crear un control que tenga tecla de acceso y ajuste de texto
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 12410e2abd1031f7ac42bdaab4b8e09a6b8b6006
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649588"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Procedimiento Crear un control que tenga tecla de acceso y ajuste de texto
En este ejemplo se explica cómo crear un control que tenga una clave de acceso y que admita el ajuste de texto. El ejemplo se usa un <xref:System.Windows.Controls.Label> control para ilustrar estos conceptos.  
  
## <a name="example"></a>Ejemplo  
 **Agregar el ajuste de texto a la etiqueta**  
  
 El <xref:System.Windows.Controls.Label> control no admite el ajuste de texto. Si necesita una etiqueta que ajuste el texto en varias líneas, puede anidar otro elemento que sí admita el ajuste de texto y colocarlo dentro de la etiqueta. El ejemplo siguiente muestra cómo usar un <xref:System.Windows.Controls.TextBlock> para crear una etiqueta que contiene varias líneas de texto.  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Agregar una tecla de acceso y el ajuste de texto a la etiqueta**  
  
 Si necesita un <xref:System.Windows.Controls.Label> que tiene una clave de acceso (tecla de acceso), use el <xref:System.Windows.Controls.AccessText> elemento que está dentro de la <xref:System.Windows.Controls.Label>.  
  
 Los controles como <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, y <xref:System.Windows.Controls.GroupBox> dispone de plantillas de control de forma predeterminada. Estas plantillas contienen un <xref:System.Windows.Controls.ContentPresenter>. Una de las propiedades que se pueden establecer en el <xref:System.Windows.Controls.ContentPresenter> es <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", que puede usar para especificar una clave de acceso para el control.  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Label> que tiene una clave de acceso y admite el ajuste de texto. Para habilitar el ajuste de texto, el ejemplo establece la <xref:System.Windows.Controls.AccessText.TextWrapping%2A> propiedad y se usa un carácter de subrayado de caracteres para especificar la clave de acceso. (El carácter que sigue inmediatamente al carácter de subrayado es la tecla de acceso).  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>Vea también
- [Cómo: Establezca la propiedad de destino de una etiqueta](https://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
