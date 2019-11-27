---
title: Agregar contenido a un cuadro de texto utilizando la UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 71385690c01d261b4ff1b495674bab377232e81d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447251"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Agregar contenido a un cuadro de texto utilizando la UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene código de ejemplo que muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para insertar texto en un cuadro de texto de una sola línea. Se proporciona un método alternativo para los controles de texto enriquecido y multilínea donde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no es aplicable. Con fines de comparación, en el ejemplo también se muestra cómo usar métodos Win32 para lograr los mismos resultados.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recorren los pasos de una secuencia de controles de texto en una aplicación de destino. Cada control de texto se comprueba para ver si un objeto de <xref:System.Windows.Automation.ValuePattern> puede obtenerse a partir de él mediante el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>. Si el control de texto admite <xref:System.Windows.Automation.ValuePattern>, se usa el método <xref:System.Windows.Automation.ValuePattern.SetValue%2A> para insertar una cadena definida por el usuario en el control de texto. De lo contrario, se utiliza el método <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de inserción de texto de TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
