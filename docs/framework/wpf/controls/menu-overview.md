---
title: Información general sobre menús
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186976"
---
# <a name="menu-overview"></a>Información general sobre menús
La <xref:System.Windows.Controls.Menu> clase permite organizar los elementos asociados con comandos y controladores de eventos en un orden jerárquico. Cada <xref:System.Windows.Controls.Menu> elemento contiene <xref:System.Windows.Controls.MenuItem> una colección de elementos.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Control Menu  
 El <xref:System.Windows.Controls.Menu> control presenta una lista de elementos que especifican comandos u opciones para una aplicación. Normalmente, al <xref:System.Windows.Controls.MenuItem> hacer clic en un se abre un submenú o hace que una aplicación lleve a cabo un comando.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>Creación de elementos Menu  
 En el ejemplo <xref:System.Windows.Controls.Menu> siguiente se <xref:System.Windows.Controls.TextBox>crea un para manipular texto en un archivo . Contiene <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.MenuItem> objetos que <xref:System.Windows.Controls.MenuItem.Command%2A> <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>utilizan <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> las propiedades <xref:System.Windows.Controls.MenuItem.Checked> <xref:System.Windows.Controls.MenuItem.Unchecked>, <xref:System.Windows.Controls.MenuItem.Click> , y los eventos , , y .  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con métodos abreviados de teclado  
 Los métodos abreviados de teclado son combinaciones <xref:System.Windows.Controls.Menu> de caracteres que se pueden introducir con el teclado para invocar comandos. Por ejemplo, la combinación de teclas para **Copiar** es CTRL+C. Hay dos propiedades para usar con los<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> métodos abreviados de teclado y los elementos de menú, o <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 En el ejemplo siguiente <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> se muestra cómo utilizar <xref:System.Windows.Controls.MenuItem> la propiedad para asignar texto de método abreviado de teclado a los controles. Esto solo coloca el método abreviado de teclado en el elemento de menú.  No asocia el comando <xref:System.Windows.Controls.MenuItem>con el archivo . La aplicación debe controlar la entrada del usuario para llevar a cabo la acción.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Get-Help  
 En el ejemplo siguiente <xref:System.Windows.Controls.MenuItem.Command%2A> se muestra cómo utilizar la <xref:System.Windows.Controls.MenuItem> propiedad para asociar los comandos **Abrir** y **Guardar** con controles. La propiedad command no solo asocia <xref:System.Windows.Controls.MenuItem>un comando a un , sino que también proporciona el texto del gesto de entrada para usarlo como método abreviado.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 La <xref:System.Windows.Controls.MenuItem> clase también <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> tiene una propiedad, que especifica el elemento donde se produce el comando. Si <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece, el elemento que tiene el foco de teclado recibe el comando. Para más información sobre los comandos, consulte [Información general sobre comandos](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>Aplicación de estilos al menú  
 Con el estilo de control, puede cambiar <xref:System.Windows.Controls.Menu> drásticamente la apariencia y el comportamiento de los controles sin tener que escribir un control personalizado. Además de establecer propiedades visuales, también puede aplicar a <xref:System.Windows.Style> partes individuales de un control, cambiar el comportamiento de partes del control a través de propiedades o agregar partes adicionales o cambiar el diseño de un control. En los ejemplos siguientes se <xref:System.Windows.Style> muestran varias maneras de agregar a a un <xref:System.Windows.Controls.Menu> control.  
  
 En el primer <xref:System.Windows.Style> ejemplo `Simple` de código se define un llamado que muestra cómo utilizar la configuración actual del sistema en el estilo. El código asigna el color de `MenuHighlightBrush` como el color de fondo del menú y `MenuTextBrush` como el color de primer plano del menú. Tenga en cuenta de que usa claves de recurso para asignar los pinceles.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 En el <xref:System.Windows.Trigger> ejemplo siguiente se utilizan elementos <xref:System.Windows.Controls.MenuItem> que permiten cambiar la <xref:System.Windows.Controls.Menu>apariencia de a en respuesta a los eventos que se producen en el archivo . Al mover el ratón <xref:System.Windows.Controls.Menu>sobre el , el color de primer plano y las características de fuente de los elementos de menú cambian.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Consulte también

- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
