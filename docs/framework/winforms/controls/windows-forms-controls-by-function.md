---
title: Controles de formularios Windows Forms por función
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: 3a82642c985b7ec1cee885cdda7b054adbe3dfee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115484"
---
# <a name="windows-forms-controls-by-function"></a>Controles de formularios Windows Forms por función
Windows Forms ofrece controles y componentes que llevan a cabo una serie de funciones. En la tabla siguiente se enumera los controles de Windows Forms y componentes según la función general. Además, donde existen varios controles que tienen la misma función, se muestra el control recomendado con una nota relacionada con el control al que reemplaza. En una tabla independiente posteriores, se muestran los controles reemplazados con sus cambios recomendados.  
  
> [!NOTE]
>  Las tablas siguientes no muestran cada control o componente que puede utilizar en formularios de Windows; Para obtener una lista más completa, consulte [controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controles y componentes por función recomendados  
  
|Función|Control|Descripción|  
|--------------|-------------|-----------------|  
|Presentación de datos|Control <xref:System.Windows.Forms.DataGridView>|El <xref:System.Windows.Forms.DataGridView> control proporciona una tabla personalizable para mostrar los datos. La <xref:System.Windows.Forms.DataGridView> clase habilita la personalización de las celdas, filas, columnas y bordes. **Nota:**  El <xref:System.Windows.Forms.DataGridView> control proporciona numerosas características básicas y avanzadas que faltan en el <xref:System.Windows.Forms.DataGrid> control. Para obtener más información, consulte [diferencias entre los Windows Forms controles DataGridView y DataGrid](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Navegación y el enlace de datos|<xref:System.Windows.Forms.BindingSource> Componente|Simplifica el enlace de controles en un formulario a los datos proporcionando gestión de divisas con notificación de cambio y otros servicios.|  
||Control <xref:System.Windows.Forms.BindingNavigator>|Proporciona una interfaz de tipo de la barra de herramientas para explorar y manipular datos en un formulario.|  
|Edición de texto|Control <xref:System.Windows.Forms.TextBox>|Muestra texto escrito en tiempo de diseño que puede ser editado por los usuarios en tiempo de ejecución, o puede cambiar mediante programación.|  
||Control <xref:System.Windows.Forms.RichTextBox>|Permite el texto que se mostrará con formato en texto sin formato o el formato de texto enriquecido (RTF).|  
||Control <xref:System.Windows.Forms.MaskedTextBox>|Restringe el formato de entrada del usuario|  
|Visualización de información (solo lectura)|Control <xref:System.Windows.Forms.Label>|Muestra texto que los usuarios no pueden modificar directamente.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra el texto como un vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial. Normalmente, el texto es un vínculo a otra ventana o un sitio Web.|  
||Control <xref:System.Windows.Forms.StatusStrip>|Muestra información sobre el estado actual de la aplicación mediante un área con marco, habitualmente en la parte inferior de un formulario principal.|  
||Control <xref:System.Windows.Forms.ProgressBar>|Muestra el progreso actual de una operación para el usuario.|  
|Presentación de una página Web|Control <xref:System.Windows.Forms.WebBrowser>|Permite al usuario navegar por páginas web dentro del formulario.|  
|Selección de una lista|Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañados por una casilla de verificación.|  
||Control <xref:System.Windows.Forms.ComboBox>|Muestra una lista desplegable de elementos.|  
||Control <xref:System.Windows.Forms.DomainUpDown>|Muestra una lista de elementos de texto que los usuarios pueden desplazarse con botones arriba y abajo.|  
||Control <xref:System.Windows.Forms.ListBox>|Muestra una lista de texto y elementos gráficos (iconos).|  
||Control <xref:System.Windows.Forms.ListView>|Muestra los elementos en uno de cuatro vistas distintas. Vistas incluyen solo texto, texto con iconos pequeños, texto con iconos grandes y una vista de detalles.|  
||Control <xref:System.Windows.Forms.NumericUpDown>|Muestra una lista de números que los usuarios pueden desplazarse con botones arriba y abajo.|  
||Control <xref:System.Windows.Forms.TreeView>|Muestra una colección jerárquica de objetos de nodo puede consistir en texto con casillas de verificación opcionales o iconos.|  
|Presentación de gráficos|Control <xref:System.Windows.Forms.PictureBox>|Muestra los archivos gráficos, como los mapas de bits e iconos, en un marco.|  
|Almacenamiento de gráficos|Control <xref:System.Windows.Forms.ImageList>|Actúa como repositorio de imágenes. <xref:System.Windows.Forms.ImageList> desde una aplicación a la siguiente, se pueden reutilizar los controles y las imágenes que contienen.|  
|Configuración del valor|Control <xref:System.Windows.Forms.CheckBox>|Muestra una casilla de verificación y una etiqueta de texto. Por lo general se usa para establecer las opciones.|  
||Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañados por una casilla de verificación.|  
||Control <xref:System.Windows.Forms.RadioButton>|Muestra un botón que se puede activar o desactivar.|  
||Control <xref:System.Windows.Forms.TrackBar>|Permite a los usuarios establecer valores en una escala moviendo un "control" a lo largo de una escala.|  
|Configuración de fecha|Control <xref:System.Windows.Forms.DateTimePicker>|Muestra un calendario gráfico para permitir a los usuarios seleccionar una fecha o una hora.|  
||Control <xref:System.Windows.Forms.MonthCalendar>|Muestra un calendario gráfico para permitir a los usuarios seleccionar un intervalo de fechas.|  
|Cuadros de diálogo|Control <xref:System.Windows.Forms.ColorDialog>|Muestra el cuadro de diálogo de selector de color que permite a los usuarios establecer el color de un elemento de interfaz.|  
||Control <xref:System.Windows.Forms.FontDialog>|Muestra un cuadro de diálogo que permite a los usuarios establezcan una fuente y sus atributos.|  
||Control <xref:System.Windows.Forms.OpenFileDialog>|Muestra un cuadro de diálogo que permite a los usuarios navegar a y seleccione un archivo.|  
||Control <xref:System.Windows.Forms.PrintDialog>|Muestra un cuadro de diálogo que permite a los usuarios seleccionar una impresora y establezca sus atributos.|  
||Control <xref:System.Windows.Forms.PrintPreviewDialog>|Muestra un cuadro de diálogo que muestra cómo un control <xref:System.Drawing.Printing.PrintDocument> componente aparecerá cuando se imprima.|  
||Control <xref:System.Windows.Forms.FolderBrowserDialog>|Muestra un cuadro de diálogo que permite a los usuarios examinar, crear y, finalmente, seleccione una carpeta|  
||Control <xref:System.Windows.Forms.SaveFileDialog>|Muestra un cuadro de diálogo que permite a los usuarios guardar un archivo.|  
|Controles de menú|Control <xref:System.Windows.Forms.MenuStrip>|Crea menús personalizados. **Nota:**  El <xref:System.Windows.Forms.MenuStrip> está diseñado para reemplazar el <xref:System.Windows.Forms.MainMenu> control.|  
||Control <xref:System.Windows.Forms.ContextMenuStrip>|Crea menús contextuales personalizados. **Nota:**  El <xref:System.Windows.Forms.ContextMenuStrip> está diseñado para reemplazar el <xref:System.Windows.Forms.ContextMenu> control.|  
|Comandos|Control <xref:System.Windows.Forms.Button>|Se inicia, detiene o interrumpe un proceso.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra el texto como un vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial. Normalmente, el texto es un vínculo a otra ventana o un sitio Web.|  
||Control <xref:System.Windows.Forms.NotifyIcon>|Muestra un icono en el área de notificación de estado de la barra de tareas que representa una aplicación que se ejecuta en segundo plano.|  
||Control <xref:System.Windows.Forms.ToolStrip>|Crea las barras de herramientas que pueden tener un Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o apariencia personalizada, con o sin temas y compatible con desbordamiento y reordenación de elementos en tiempo de ejecución. **Nota:**  El <xref:System.Windows.Forms.ToolStrip> control está diseñado para reemplazar el <xref:System.Windows.Forms.ToolBar> control.|  
|Ayuda de usuario|<xref:System.Windows.Forms.HelpProvider> Componente|Proporciona Ayuda en línea o en cuadros emergentes para los controles.|  
||<xref:System.Windows.Forms.ToolTip> Componente|Proporciona una ventana emergente que muestra una breve descripción del propósito de un control cuando el usuario sitúa el puntero sobre el control.|  
|Agrupar otros controles|Control <xref:System.Windows.Forms.Panel>|Agrupa un conjunto de controles en un marco desplazable sin etiqueta.|  
||Control <xref:System.Windows.Forms.GroupBox>|Agrupa un conjunto de controles (como botones de radio) en un marco con etiqueta, de no desplazable.|  
||Control <xref:System.Windows.Forms.TabControl>|Proporciona una página con pestañas para organizar y obtener acceso a objetos agrupados de forma eficaz.|  
||Control <xref:System.Windows.Forms.SplitContainer>|Proporciona dos paneles separados por una barra móvil. **Nota:**  El <xref:System.Windows.Forms.SplitContainer> control está diseñado para reemplazar el <xref:System.Windows.Forms.Splitter> control.|  
||Control <xref:System.Windows.Forms.TableLayoutPanel>|Representa un panel que dispone dinámicamente su contenido en una cuadrícula que se compone de filas y columnas.|  
||Control <xref:System.Windows.Forms.FlowLayoutPanel>|Representa un panel que dispone dinámicamente su contenido horizontal o verticalmente.|  
|Audio|Control <xref:System.Media.SoundPlayer>|Archivos de sonido se reproduce en el formato .wav. Sonidos se pueden cargar o reproducir de forma asincrónica.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Controles y componentes por función reemplazados  
  
|Función|Control reemplazado|Reemplazo recomendado|  
|--------------|------------------------|-----------------------------|  
|Presentación de datos|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Visualización de información (controles de solo lectura)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Controles de menú|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Comandos|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Diseño de formulario|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Vea también

- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)
