---
title: "Controles de formularios Windows Forms por funci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], por función"
  - "controles de Windows Forms, lista"
  - "Windows Forms, controles por función"
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Controles de formularios Windows Forms por funci&#243;n
Los formularios Windows Forms proporcionan controles y componentes que realizan varias funciones.  En la tabla siguiente se muestran los controles y componentes de formularios Windows Forms según la función general.  Además, donde existen varios controles que atienden la misma función, se muestra el control recomendado con una nota en relación con el control al que reemplaza.  En una tabla subsiguiente independiente, se muestran los controles reemplazados con sus reemplazos recomendados.  
  
> [!NOTE]
>  En las tablas siguientes no se muestran todos los controles o componentes que puede utilizar en formularios Windows Forms; para una lista más completa, vea [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## Controles y componentes recomendados por función  
  
|Función|Control|Descripción|  
|-------------|-------------|-----------------|  
|Presentación de datos|Control <xref:System.Windows.Forms.DataGridView>|El control <xref:System.Windows.Forms.DataGridView> proporciona una tabla personalizable para mostrar datos.  La clase <xref:System.Windows.Forms.DataGridView> habilita la personalización de celdas, filas, columnas y bordes. **Note:**  El control <xref:System.Windows.Forms.DataGridView> proporciona muchas características básicas y avanzadas que faltan en el control <xref:System.Windows.Forms.DataGrid>.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).|  
|Enlace de datos y navegación|Componente <xref:System.Windows.Forms.BindingSource>|Simplifica el enlace de controles en un formulario a los datos proporcionando la administración de la divisa, la notificación de cambios y otros servicios.|  
||Control <xref:System.Windows.Forms.BindingNavigator>|Proporciona una interfaz tipo barra de herramientas para navegar y manipular los datos en un formulario.|  
|Edición de texto|Control <xref:System.Windows.Forms.TextBox>|Muestra texto escrito en tiempo de diseño que puede ser editado por los usuarios en tiempo de ejecución o ser modificado mediante programación.|  
||Control <xref:System.Windows.Forms.RichTextBox>|Habilita la presentación de texto sin formato o de texto enriquecido \(RTF\).|  
||Control <xref:System.Windows.Forms.MaskedTextBox>|Restringe el formato de los datos proporcionados por el usuario|  
|Presentación de la información \(solo lectura\)|Control <xref:System.Windows.Forms.Label>|Muestra texto que los usuarios no pueden modificar directamente.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra texto en forma de vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial.  Habitualmente, el texto es un vínculo a otra ventana o a un sitio Web.|  
||Control <xref:System.Windows.Forms.StatusStrip>|Muestra información acerca del estado actual de la aplicación mediante un área con marco, habitualmente en la parte inferior de un formulario primario.|  
||Control <xref:System.Windows.Forms.ProgressBar>|Muestra el progreso actual de una operación al usuario.|  
|Presentación de página Web|Control <xref:System.Windows.Forms.WebBrowser>|Permite al usuario navegar por páginas Web dentro del formulario.|  
|Selección de una lista|Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañado por una casilla.|  
||Control <xref:System.Windows.Forms.ComboBox>|Muestra una lista desplegable de elementos.|  
||Control <xref:System.Windows.Forms.DomainUpDown>|Muestra una lista de elementos de texto a través de la cual los usuarios se pueden desplazar mediante botones hacia arriba y hacia abajo.|  
||Control <xref:System.Windows.Forms.ListBox>|Muestra una lista de texto y elementos gráficos \(iconos\).|  
||control <xref:System.Windows.Forms.ListView>|Muestra los elementos por medio de una de cuatro vistas diferentes.  Las vistas son Sólo texto, Texto con iconos pequeños, Texto con iconos grandes y una vista Detalles.|  
||Control <xref:System.Windows.Forms.NumericUpDown>|Muestra una lista de números a través de la cual los usuarios se pueden desplazar mediante botones hacia arriba y hacia abajo.|  
||control <xref:System.Windows.Forms.TreeView>|Muestra una colección jerárquica de objetos de nodo que pueden constar de texto con casillas o iconos opcionales.|  
|Presentación de gráficos|Control <xref:System.Windows.Forms.PictureBox>|Muestra archivos gráficos, tales como mapas de bits e iconos, en un marco.|  
|Almacenamiento de gráficos|Control <xref:System.Windows.Forms.ImageList>|Actúa como un repositorio para las imágenes.  Los controles <xref:System.Windows.Forms.ImageList> y las imágenes que contienen se pueden reutilizar de una aplicación a la siguiente.|  
|Establecimiento de valores|Control <xref:System.Windows.Forms.CheckBox>|Muestra una casilla y una etiqueta para texto.  Se utiliza en general para establecer opciones.|  
||Control <xref:System.Windows.Forms.CheckedListBox>|Muestra una lista desplazable de elementos, cada uno acompañado por una casilla.|  
||Control <xref:System.Windows.Forms.RadioButton>|Muestra un botón que puede activarse o desactivarse.|  
||Control <xref:System.Windows.Forms.TrackBar>|Permite que los usuarios establezcan valores mediante el desplazamiento de un control de posición a lo largo de una escala.|  
|Establecimiento de fechas|Control <xref:System.Windows.Forms.DateTimePicker>|Muestra un calendario gráfico que permite que los usuarios seleccionen una fecha o una hora.|  
||Control <xref:System.Windows.Forms.MonthCalendar>|Muestra un calendario gráfico que permite que los usuarios seleccionen un intervalo de fechas.|  
|Cuadros de diálogo|Control <xref:System.Windows.Forms.ColorDialog>|Muestra el cuadro de diálogo de selección de colores, que permite que los usuarios seleccionen el color de un elemento de la interfaz.|  
||Control <xref:System.Windows.Forms.FontDialog>|Muestra un cuadro de diálogo que permite que los usuarios establezcan una fuente y sus atributos.|  
||Control <xref:System.Windows.Forms.OpenFileDialog>|Muestra un cuadro de diálogo que permite que los usuarios naveguen hasta un archivo y lo seleccionen.|  
||Control <xref:System.Windows.Forms.PrintDialog>|Muestra un cuadro de diálogo que permite que los usuarios seleccionen una impresora y sus atributos.|  
||Control <xref:System.Windows.Forms.PrintPreviewDialog>|Muestra un cuadro de diálogo que muestra cómo aparecerá un componente <xref:System.Drawing.Printing.PrintDocument> de control al imprimirse.|  
||Control <xref:System.Windows.Forms.FolderBrowserDialog>|Muestra un cuadro de diálogo que permite que los usuarios examinen, creen y finalmente seleccionen una carpeta|  
||Control <xref:System.Windows.Forms.SaveFileDialog>|Muestra un cuadro de diálogo que permite que los usuarios guarden un archivo.|  
|Controles de menú|Control <xref:System.Windows.Forms.MenuStrip>|Crea los menús personalizados. **Note:**  Se ha diseñado <xref:System.Windows.Forms.MenuStrip> para reemplazar al control <xref:System.Windows.Forms.MainMenu>.|  
||Control <xref:System.Windows.Forms.ContextMenuStrip>|Crea menús de acceso directo personalizados. **Note:**  Se ha diseñado <xref:System.Windows.Forms.ContextMenuStrip> para reemplazar al control <xref:System.Windows.Forms.ContextMenu>.|  
|Comandos|Control <xref:System.Windows.Forms.Button>|Inicia, detiene o interrumpe un proceso.|  
||Control <xref:System.Windows.Forms.LinkLabel>|Muestra texto en forma de vínculo de estilo Web y desencadena un evento cuando el usuario hace clic en el texto especial.  Habitualmente, el texto es un vínculo a otra ventana o a un sitio Web.|  
||Control <xref:System.Windows.Forms.NotifyIcon>|Muestra un icono, en el área de notificación de estado de la barra de tareas, que representa una aplicación que se ejecuta en segundo plano.|  
||Control <xref:System.Windows.Forms.ToolStrip>|Crea barras de herramientas que pueden tener un aspecto y un diseño de Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o personalizado, con o sin temas y que admiten el desbordamiento y la reordenación de elementos en tiempo de ejecución. **Note:**  Se ha diseñado el control <xref:System.Windows.Forms.ToolStrip> para reemplazar al control <xref:System.Windows.Forms.ToolBar>.|  
|Ayuda del usuario|Componente <xref:System.Windows.Forms.HelpProvider>|Proporciona Ayuda emergente o en pantalla relativa a los controles.|  
||Componente <xref:System.Windows.Forms.ToolTip>|Proporciona una ventana emergente que muestra una breve descripción de para qué sirve un control cuando el usuario coloca el puntero sobre el control.|  
|Agrupar otros controles|Control <xref:System.Windows.Forms.Panel>|Agrupa un conjunto de controles en un marco sin etiqueta que permite el desplazamiento.|  
||Control <xref:System.Windows.Forms.GroupBox>|Agrupa un conjunto de controles \(tales como botones de radio\) en un marco con etiqueta, que no permite el desplazamiento.|  
||Control <xref:System.Windows.Forms.TabControl>|Proporciona una página con fichas para organizar y tener acceso a controles agrupados de forma eficiente.|  
||Control <xref:System.Windows.Forms.SplitContainer>|Proporciona dos paneles separados por una barra movible. **Note:**  Se ha diseñado el control <xref:System.Windows.Forms.SplitContainer> para reemplazar al control <xref:System.Windows.Forms.Splitter>.|  
||Control <xref:System.Windows.Forms.TableLayoutPanel>|Representa un panel que dispone dinámicamente su contenido en una cuadrícula que se compone de filas y columnas.|  
||Control <xref:System.Windows.Forms.FlowLayoutPanel>|Representa un panel que dispone dinámicamente su contenido en posición horizontal o vertical.|  
|Audio|Control <xref:System.Media.SoundPlayer>|Reproduce los archivos de sonido en el formato .wav.  Se pueden cargar o reproducirse los sonidos de forma asincrónica.|  
  
## Controles y componentes reemplazados por función  
  
|Función|Control reemplazado|Reemplazo recomendado|  
|-------------|-------------------------|---------------------------|  
|Presentación de datos|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Presentación de información \(controles de sólo lectura\)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Controles de menú|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Comandos|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Diseño de formulario|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## Vea también  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)