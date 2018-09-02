---
title: Información general sobre menús
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: a1074d09c195a78dcc79df0841123672b716bcfe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423117"
---
# <a name="menu-overview"></a>Información general sobre menús
La <xref:System.Windows.Controls.Menu> clase le permite organizar los elementos asociados a comandos y controladores de eventos en un orden jerárquico. Cada <xref:System.Windows.Controls.Menu> elemento contiene una colección de <xref:System.Windows.Controls.MenuItem> elementos.  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Control Menu  
 El <xref:System.Windows.Controls.Menu> control presenta una lista de elementos que especifican comandos u opciones para una aplicación. Normalmente, al hacer clic en un <xref:System.Windows.Controls.MenuItem> abre un submenú o provoca que una aplicación para llevar a cabo un comando.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Creación de elementos Menu  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Menu> para manipular texto en un <xref:System.Windows.Controls.TextBox>. El <xref:System.Windows.Controls.Menu> contiene <xref:System.Windows.Controls.MenuItem> los objetos que utilizan el <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, y <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedades y el <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, y <xref:System.Windows.Controls.MenuItem.Click> eventos.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con métodos abreviados de teclado  
 Métodos abreviados de teclado son combinaciones de caracteres que se pueden escribir con el teclado para invocar <xref:System.Windows.Controls.Menu> comandos. Por ejemplo, la combinación de teclas para **Copiar** es CTRL+C. Hay dos propiedades para usar con elementos de menú y métodos abreviados de teclado:<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> propiedad para asignar el texto de método abreviado de teclado para <xref:System.Windows.Controls.MenuItem> controles. Esto solo coloca el método abreviado de teclado en el elemento de menú.  No asocia el comando con el <xref:System.Windows.Controls.MenuItem>. La aplicación debe controlar la entrada del usuario para llevar a cabo la acción.  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Comando  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.MenuItem.Command%2A> propiedad para asociar el **abierto** y **guardar** comandos con <xref:System.Windows.Controls.MenuItem> controles. No solo la propiedad command asociar un comando con un <xref:System.Windows.Controls.MenuItem>, sino que también proporciona el texto de gesto de entrada que se usará como un acceso directo.  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 El <xref:System.Windows.Controls.MenuItem> clase también tiene un <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> propiedad, que especifica el elemento donde se produce el comando. Si <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no está establecido, el elemento que tiene el foco de teclado recibe el comando. Para más información sobre los comandos, consulte [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Aplicación de estilos al menú  
 Con los estilos de control, puede cambiar drásticamente la apariencia y comportamiento de <xref:System.Windows.Controls.Menu> controles sin tener que escribir un control personalizado. Además de establecer las propiedades visuales, también puede aplicar un <xref:System.Windows.Style> a las partes individuales de un control, cambiar el comportamiento de las partes del control mediante propiedades, o agregar partes adicionales o cambiar el diseño de un control. Los ejemplos siguientes muestran varias maneras de agregar un <xref:System.Windows.Style> a un <xref:System.Windows.Controls.Menu> control.  
  
 El primer ejemplo de código define un <xref:System.Windows.Style> llamado `Simple` que muestra cómo usar la configuración actual del sistema en el estilo. El código asigna el color de `MenuHighlightBrush` como el color de fondo del menú y `MenuTextBrush` como el color de primer plano del menú. Tenga en cuenta de que usa claves de recurso para asignar los pinceles.  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 El ejemplo siguiente usa <xref:System.Windows.Trigger> elementos que le permiten cambiar la apariencia de un <xref:System.Windows.Controls.MenuItem> en respuesta a eventos que se producen en el <xref:System.Windows.Controls.Menu>. Cuando mueva el mouse sobre el <xref:System.Windows.Controls.Menu>, el color de primer plano y cambiar las características de fuente de los elementos de menú.  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Vea también  
 [WPF Controls Gallery Sample](https://go.microsoft.com/fwlink/?LinkID=160053) (Ejemplo de galería de controles de WPF)
