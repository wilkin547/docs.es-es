---
title: Información general sobre menús
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124655"
---
# <a name="menu-overview"></a>Información general sobre menús
La clase <xref:System.Windows.Controls.Menu> permite organizar los elementos asociados a comandos y controladores de eventos en un orden jerárquico. Cada elemento <xref:System.Windows.Controls.Menu> contiene una colección de elementos <xref:System.Windows.Controls.MenuItem>.  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Control Menu  
 El control <xref:System.Windows.Controls.Menu> presenta una lista de elementos que especifican comandos u opciones para una aplicación. Normalmente, al hacer clic en un <xref:System.Windows.Controls.MenuItem> se abre un submenú o se hace que una aplicación lleve a cabo un comando.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Creación de elementos Menu  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Menu> para manipular texto en un <xref:System.Windows.Controls.TextBox>. El <xref:System.Windows.Controls.Menu> contiene <xref:System.Windows.Controls.MenuItem> objetos que utilizan las propiedades <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>y <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> y los eventos <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>y <xref:System.Windows.Controls.MenuItem.Click>.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con métodos abreviados de teclado  
 Los métodos abreviados de teclado son combinaciones de caracteres que se pueden escribir con el teclado para invocar <xref:System.Windows.Controls.Menu> comandos. Por ejemplo, la combinación de teclas para **Copiar** es CTRL+C. Hay dos propiedades que se pueden usar con los métodos abreviados de teclado y los elementos de menú:<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 En el ejemplo siguiente se muestra cómo usar la propiedad <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> para asignar texto de método abreviado de teclado a controles de <xref:System.Windows.Controls.MenuItem>. Esto solo coloca el método abreviado de teclado en el elemento de menú.  No asocia el comando al <xref:System.Windows.Controls.MenuItem>. La aplicación debe controlar la entrada del usuario para llevar a cabo la acción.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Get-Help  
 En el ejemplo siguiente se muestra cómo utilizar la propiedad <xref:System.Windows.Controls.MenuItem.Command%2A> para asociar los comandos **abrir** y **guardar** con controles <xref:System.Windows.Controls.MenuItem>. No solo la propiedad de comando asocia un comando a un <xref:System.Windows.Controls.MenuItem>, sino que también proporciona el texto de gestos de entrada que se va a usar como método abreviado.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 La clase <xref:System.Windows.Controls.MenuItem> también tiene una propiedad <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>, que especifica el elemento en el que se produce el comando. Si no se establece <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>, el elemento que tiene el foco de teclado recibe el comando. Para más información sobre los comandos, consulte [Información general sobre comandos](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Aplicación de estilos al menú  
 Con el estilo del control, puede cambiar drásticamente la apariencia y el comportamiento de los controles de <xref:System.Windows.Controls.Menu> sin tener que escribir un control personalizado. Además de establecer las propiedades visuales, también puede aplicar un <xref:System.Windows.Style> a partes individuales de un control, cambiar el comportamiento de las partes del control a través de las propiedades o agregar elementos adicionales o cambiar el diseño de un control. En los ejemplos siguientes se muestran varias maneras de agregar un <xref:System.Windows.Style> a un control <xref:System.Windows.Controls.Menu>.  
  
 En el primer ejemplo de código se define una <xref:System.Windows.Style> llamada `Simple` que muestra cómo usar la configuración actual del sistema en el estilo. El código asigna el color de `MenuHighlightBrush` como el color de fondo del menú y `MenuTextBrush` como el color de primer plano del menú. Tenga en cuenta de que usa claves de recurso para asignar los pinceles.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 En el ejemplo siguiente se usa <xref:System.Windows.Trigger> elementos que permiten cambiar la apariencia de un <xref:System.Windows.Controls.MenuItem> en respuesta a los eventos que se producen en el <xref:System.Windows.Controls.Menu>. Al pasar el mouse sobre el <xref:System.Windows.Controls.Menu>, cambian el color de primer plano y las características de fuente de los elementos de menú.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Consulte también

- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
