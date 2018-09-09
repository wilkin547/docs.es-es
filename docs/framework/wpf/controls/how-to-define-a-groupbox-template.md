---
title: 'Cómo: Definir una plantilla de un control GroupBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: a47ce896be4d1c38147584dd80b1bc841737d526
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227027"
---
# <a name="how-to-define-a-groupbox-template"></a>Cómo: Definir una plantilla de un control GroupBox
En este ejemplo se muestra cómo crear una plantilla para un <xref:System.Windows.Controls.GroupBox> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Controls.GroupBox> plantilla de control mediante el uso de un <xref:System.Windows.Controls.Grid> control para el diseño. La plantilla utiliza un <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde de la <xref:System.Windows.Controls.GroupBox> para que el borde no oculte el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenido.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GroupBox>  
 [Temas de procedimientos de GroupBox](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
