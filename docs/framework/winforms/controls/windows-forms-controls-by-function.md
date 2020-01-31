---
title: Controles por función
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: f2341d49513b418c244ee7ab93c0858899502487
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741579"
---
# <a name="windows-forms-controls-by-function"></a>Controles de Windows Forms por función
Windows Forms ofrece controles y componentes que realizan una serie de funciones. En la tabla siguiente se enumeran los controles y componentes de Windows Forms según la función general. Además, cuando existen varios controles que sirven a la misma función, el control recomendado se muestra con una nota relacionada con el control que se ha reemplazado. En una tabla posterior independiente, los controles sustituidos se enumeran con los reemplazos recomendados.  
  
> [!NOTE]
> En las tablas siguientes no se enumeran todos los controles o componentes que se pueden usar en Windows Forms; para obtener una lista más completa, vea [controles que se usan en Windows Forms](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controles y componentes recomendados por función  
  
|Función|Control|Descripción|  
|--------------|-------------|-----------------|  
|Presentación de datos|Control <xref:System.Windows.Forms.DataGridView>|El control <xref:System.Windows.Forms.DataGridView> proporciona una tabla personalizable para mostrar los datos. La clase <xref:System.Windows.Forms.DataGridView> permite personalizar celdas, filas, columnas y bordes. **Nota:**  El control <xref:System.Windows.Forms.DataGridView> proporciona numerosas características básicas y avanzadas que faltan en el control <xref:System.Windows.Forms.DataGrid>. Para obtener más información, vea [diferencias entre los controles Windows Forms DataGridView y DataGrid](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) .|  
|Enlace y navegación de datos|<xref:System.Windows.Forms.BindingSource> componente|Simplifica los controles de enlace de un formulario a los datos proporcionando administración de moneda, notificación de cambios y otros servicios.|  
||Control <xref:System.Windows.Forms.BindingNavigator>|Proporciona una interfaz de tipo barra de herramientas para navegar por los datos de un formulario y manipularlos.|  
|Edición de texto|Control <xref:System.Windows.Forms.TextBox>|Muestra el texto especificado en tiempo de diseño que pueden editar los usuarios en tiempo de ejecución, o que se pueden cambiar mediante programación.|  
||Control <xref:System.Windows.Forms.RichTextBox>|Permite mostrar el texto con formato en texto sin formato o en formato de texto enriquecido (RTF).|  
||Control <xref:System.Windows.Forms.MaskedTextBox>|Restringe el formato de los datos proporcionados por el usuario|  
|Pantalla de información (solo lectura)|Control <xref:System.Windows.Forms.Label>|Muestra texto que los usuarios no pueden modificar directamente.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra el texto como un vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial. Normalmente, el texto es un vínculo a otra ventana o un sitio Web.|  
||Control <xref:System.Windows.Forms.StatusStrip>|Muestra información sobre el estado actual de la aplicación mediante un área de marco, normalmente en la parte inferior de un formulario primario.|  
||Control <xref:System.Windows.Forms.ProgressBar>|Muestra el progreso actual de una operación al usuario.|  
|Presentación de la página web|Control <xref:System.Windows.Forms.WebBrowser>|Permite al usuario navegar por páginas web dentro del formulario.|  
|Selección de una lista|Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañado de una casilla.|  
||Control <xref:System.Windows.Forms.ComboBox>|Muestra una lista desplegable de elementos.|  
||Control <xref:System.Windows.Forms.DomainUpDown>|Muestra una lista de elementos de texto en los que los usuarios pueden desplazarse con los botones arriba y abajo.|  
||Control <xref:System.Windows.Forms.ListBox>|Muestra una lista de texto y elementos gráficos (iconos).|  
||Control <xref:System.Windows.Forms.ListView>|Muestra los elementos en una de las cuatro vistas diferentes. Las vistas incluyen solo texto, texto con iconos pequeños, texto con iconos grandes y una vista de detalles.|  
||Control <xref:System.Windows.Forms.NumericUpDown>|Muestra una lista de números que los usuarios pueden desplazarse por los botones arriba y abajo.|  
||Control <xref:System.Windows.Forms.TreeView>|Muestra una colección jerárquica de objetos de nodo que pueden constar de texto con casillas de verificación o iconos opcionales.|  
|Visualización de gráficos|Control <xref:System.Windows.Forms.PictureBox>|Muestra archivos gráficos, como mapas de bits e iconos, en un marco.|  
|Almacenamiento de gráficos|Control <xref:System.Windows.Forms.ImageList>|Sirve como repositorio para las imágenes. <xref:System.Windows.Forms.ImageList> controles y las imágenes que contienen se pueden volver a usar desde una aplicación a la siguiente.|  
|Valor de configuración|Control <xref:System.Windows.Forms.CheckBox>|Muestra una casilla y una etiqueta para el texto. Se utiliza normalmente para establecer opciones.|  
||Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañado de una casilla.|  
||Control <xref:System.Windows.Forms.RadioButton>|Muestra un botón que se puede activar o desactivar.|  
||Control <xref:System.Windows.Forms.TrackBar>|Permite a los usuarios establecer valores en una escala moviendo un "control de posición" a lo largo de una escala.|  
|Configuración de fecha|Control <xref:System.Windows.Forms.DateTimePicker>|Muestra un calendario gráfico que permite a los usuarios seleccionar una fecha o una hora.|  
||Control <xref:System.Windows.Forms.MonthCalendar>|Muestra un calendario gráfico que permite a los usuarios seleccionar un intervalo de fechas.|  
|Cuadros de diálogo|Control <xref:System.Windows.Forms.ColorDialog>|Muestra el cuadro de diálogo Selector de colores que permite a los usuarios establecer el color de un elemento de la interfaz.|  
||Control <xref:System.Windows.Forms.FontDialog>|Muestra un cuadro de diálogo que permite a los usuarios establecer una fuente y sus atributos.|  
||Control <xref:System.Windows.Forms.OpenFileDialog>|Muestra un cuadro de diálogo que permite a los usuarios navegar y seleccionar un archivo.|  
||Control <xref:System.Windows.Forms.PrintDialog>|Muestra un cuadro de diálogo que permite a los usuarios seleccionar una impresora y establecer sus atributos.|  
||Control <xref:System.Windows.Forms.PrintPreviewDialog>|Muestra un cuadro de diálogo que muestra cómo aparecerá un control <xref:System.Drawing.Printing.PrintDocument> componente cuando se imprima.|  
||Control <xref:System.Windows.Forms.FolderBrowserDialog>|Muestra un cuadro de diálogo que permite a los usuarios examinar, crear y, finalmente, seleccionar una carpeta.|  
||Control <xref:System.Windows.Forms.SaveFileDialog>|Muestra un cuadro de diálogo que permite a los usuarios guardar un archivo.|  
|Controles de menú|Control <xref:System.Windows.Forms.MenuStrip>|Crea menús personalizados. **Nota:**  El <xref:System.Windows.Forms.MenuStrip> está diseñado para reemplazar el control <xref:System.Windows.Forms.MainMenu>.|  
||Control <xref:System.Windows.Forms.ContextMenuStrip>|Crea menús contextuales personalizados. **Nota:**  El <xref:System.Windows.Forms.ContextMenuStrip> está diseñado para reemplazar el control <xref:System.Windows.Forms.ContextMenu>.|  
|Comandos|Control <xref:System.Windows.Forms.Button>|Inicia, detiene o interrumpe un proceso.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra el texto como un vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial. Normalmente, el texto es un vínculo a otra ventana o un sitio Web.|  
||Control <xref:System.Windows.Forms.NotifyIcon>|Muestra un icono en el área de notificación de estado de la barra de tareas que representa una aplicación que se ejecuta en segundo plano.|  
||Control <xref:System.Windows.Forms.ToolStrip>|Crea barras de herramientas que pueden tener Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o apariencia personalizada, con o sin temas, y con compatibilidad con la reordenación de elementos de tiempo de ejecución y desbordamiento. **Nota:**  El control <xref:System.Windows.Forms.ToolStrip> está diseñado para reemplazar el control <xref:System.Windows.Forms.ToolBar>.|  
|Ayuda del usuario|<xref:System.Windows.Forms.HelpProvider> componente|Proporciona Ayuda en línea o en cuadros emergentes para los controles.|  
||<xref:System.Windows.Forms.ToolTip> componente|Proporciona una ventana emergente que muestra una breve descripción de la finalidad de un control cuando el usuario coloca el puntero sobre el control.|  
|Agrupar otros controles|Control <xref:System.Windows.Forms.Panel>|Agrupa un conjunto de controles en un marco desplazable sin etiquetar.|  
||Control <xref:System.Windows.Forms.GroupBox>|Agrupa un conjunto de controles (como botones de radio) en un marco con etiqueta y no desplazable.|  
||Control <xref:System.Windows.Forms.TabControl>|Proporciona una página con pestañas para organizar y obtener acceso a objetos agrupados de forma eficaz.|  
||Control <xref:System.Windows.Forms.SplitContainer>|Proporciona dos paneles separados por una barra movible. **Nota:**  El control <xref:System.Windows.Forms.SplitContainer> está diseñado para reemplazar el control <xref:System.Windows.Forms.Splitter>.|  
||Control <xref:System.Windows.Forms.TableLayoutPanel>|Representa un panel que dispone dinámicamente su contenido en una cuadrícula que se compone de filas y columnas.|  
||Control <xref:System.Windows.Forms.FlowLayoutPanel>|Representa un panel que dispone dinámicamente su contenido horizontal o verticalmente.|  
|Audio|Control <xref:System.Media.SoundPlayer>|Reproduce archivos de sonido en el formato. wav. Los sonidos se pueden cargar o reproducir de forma asincrónica.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Controles y componentes reemplazados por función  
  
|Función|Control reemplazado|Reemplazo recomendado|  
|--------------|------------------------|-----------------------------|  
|Presentación de datos|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Pantalla de información (controles de solo lectura)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Controles de menú|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Comandos|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Diseño de formulario|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Vea también

- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)
