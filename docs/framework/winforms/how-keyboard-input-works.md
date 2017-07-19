---
title: "How Keyboard Input Works | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "keyboard input, about keyboard input"
  - "keyboards, keyboard input"
  - "Windows Forms, keyboard input"
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# How Keyboard Input Works
Los formularios Windows Forms procesan las acciones del teclado provocando eventos de teclado en respuesta a los mensajes de Windows.  La mayoría de las aplicaciones de Windows Forms procesan exclusivamente las acciones del teclado controlando los eventos de teclado.  No obstante, es necesario comprender cómo funcionan los mensajes del teclado de modo que pueda implementar casos de acción del teclado avanzados, como interceptar teclas antes de que lleguen a un control.  En este tema se describen los tipos de datos de tecla que los formularios Windows Forms reconocen y se proporciona información general de cómo se enrutan los mensajes del teclado.  Para obtener información sobre los eventos de teclado, vea [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md).  
  
## Tipos de teclas  
 Los formularios Windows Forms identifican las acciones del teclado como códigos de tecla virtual que se representan por la enumeración <xref:System.Windows.Forms.Keys> bit a bit.  Con la enumeración <xref:System.Windows.Forms.Keys>, puede combinar una serie de teclas presionadas para producir un valor único.  Estos valores corresponden a los valores que acompañan los mensajes de Windows WM\_KEYDOWN y WM\_SYSKEYDOWN.  Puede detectar la mayoría de las presiones de tecla físicas controlando los eventos <xref:System.Windows.Forms.Control.KeyDown> o <xref:System.Windows.Forms.Control.KeyUp>.  Las teclas de carácter son un subconjunto de la enumeración <xref:System.Windows.Forms.Keys> y corresponden a los valores que acompañan los mensajes de Windows WM\_CHAR y WM\_SYSCHAR.  Si la combinación de teclas presionadas produce un carácter, puede detectar el carácter controlando el evento <xref:System.Windows.Forms.Control.KeyPress>.  Alternativamente, puede utilizar <xref:Microsoft.VisualBasic.Devices.Keyboard>, expuesto por la interfaz de programación en Visual Basic, para detectar qué teclas se han presionado y enviar las teclas.  Para obtener más información, vea [Acceso al teclado](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md).  
  
## Orden de eventos de teclado  
 Como se muestra previamente, hay 3 eventos relacionados con el teclado que pueden aparecer en un control.  La secuencia siguiente muestra el orden general de los eventos:  
  
1.  El usuario presiona la tecla "a", se preprocesa la tecla, se envía y se produce un evento <xref:System.Windows.Forms.Control.KeyDown>.  
  
2.  El usuario mantiene presionada la tecla "a", se preprocesa la tecla, se envía y se produce un evento <xref:System.Windows.Forms.Control.KeyPress>.  
  
     Este evento aparece varias veces cuando el usuario mantiene presionada una tecla.  
  
3.  El usuario libera la tecla "a", se preprocesa la tecla, se envía y se produce un evento <xref:System.Windows.Forms.Control.KeyUp>.  
  
## Preprocesar teclas  
 Como otros mensajes, los mensajes del teclado se procesan en el método <xref:System.Windows.Forms.Control.WndProc%2A> de un formulario o control.  No obstante, antes de que se procesan los mensajes del teclado, el método <xref:System.Windows.Forms.Control.PreProcessMessage%2A> llama a uno o varios métodos que se pueden reemplazar para controlar teclas de caracteres especiales y teclas físicas.  Puede reemplazar estos métodos para detectar y filtrar determinadas teclas antes de que el control procese los mensajes.  En la tabla siguiente se muestra la acción que se realiza y el método relacionado que aparece, en el orden en que aparece el método.  
  
### Preprocesar eventos KeyDown  
  
|Acción|Método relacionado|Notas|  
|------------|------------------------|-----------|  
|Comprobar si es una tecla de comando como un acelerador o una tecla de acceso a menú.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Este método procesa una tecla de comando, que tiene prioridad sobre las teclas normales.  Si este método devuelve `true`, no se envía el mensaje de tecla y no se produce un evento Key.  Si devuelve `false`, se llama al método <xref:System.Windows.Forms.Control.IsInputKey%2A>`.`|  
|Comprobar si es una tecla especial que necesita un procesamiento previo o una tecla de carácter normal que debe generar un evento <xref:System.Windows.Forms.Control.KeyDown> y enviarse a un control.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Si el método devuelve `true`, significa que el control es un carácter normal y se provoca un evento <xref:System.Windows.Forms.Control.KeyDown>.  Si es `false`, se llama al método <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>. **Note:**  Para garantizar que un control obtiene una tecla o combinación de teclas, puede controlar el evento <xref:System.Windows.Forms.Control.PreviewKeyDown> y establecer <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> de <xref:System.Windows.Forms.PreviewKeyDownEventArgs> en `true` para la tecla o teclas deseadas.|  
|Comprobar si es una tecla de navegación \(ESC, TAB, Retorno o teclas de dirección\).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Este método procesa una clave física que emplea la funcionalidad especial dentro del control, como cambiar el foco entre el control y su elemento primario.  Si el control inmediato no controla la tecla, se llama al método <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> en el control primario y así sucesivamente hasta el control más superior en la jerarquía.  Si este método devuelve `true`, finaliza el preprocesamiento y no se genera un evento Key.  Si devuelve `false`, se produce un evento <xref:System.Windows.Forms.Control.KeyDown>.|  
  
### Preprocesar eventos KeyPress  
  
|Acción|Método relacionado|Notas|  
|------------|------------------------|-----------|  
|Comprobar si la tecla es un carácter normal que debería ser procesado por el control|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Si el carácter es un carácter normal, este método devuelve `true`, se provoca el evento <xref:System.Windows.Forms.Control.KeyPress> y no se produce ningún preprocesamiento más.  De lo contrario se llamará a <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Comprobar si el carácter es un código de tecla de acceso \(como &Aceptar en un botón\)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Este método, similar a <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, lo llamará el superior en la jerarquía del control.  Si el control es un control contenedor, comprueba si hay teclas de acceso llamando a <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> en él y sus controles secundarios.  Si <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> devuelve `true`, no se produce un evento <xref:System.Windows.Forms.Control.KeyPress>.|  
  
## Procesar messages del teclado  
 Después de que los mensajes del teclado llegan al método <xref:System.Windows.Forms.Control.WndProc%2A> de un formulario o control, un conjunto de métodos que se pueden reemplazar los procesa.  Cada uno de estos métodos devuelve un valor <xref:System.Boolean> que especifica si se ha procesado el mensaje del teclado y lo ha utilizado el control.  Si uno de los métodos devuelve `true`, se considera que se ha controlado el mensaje y no se pasa al base o primario del control para más procesamiento.  De lo contrario, el mensaje permanece en la Message Queue y se puede procesar en otro método del base o primario del control.  En la tabla siguiente se presentan los métodos que procesan los mensajes del teclado.  
  
|Método|Notas|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Este método procesa todos los mensajes del teclado que son recibidos por el método <xref:System.Windows.Forms.Control.WndProc%2A> del control.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Este método envía el mensaje del teclado al elemento primario del control.  Si <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> devuelve `true`, no se genera ningún evento Key, de lo contrario se llama a <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Este método provoca los eventos <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> y <xref:System.Windows.Forms.Control.KeyUp>, según corresponda.|  
  
## Reemplazar métodos de teclado  
 Hay muchos métodos disponibles para reemplazar cuando se preprocesa y procesa un mensaje del teclado; sin embargo, algunos métodos son opciones mucho mejores que otros.  En la tabla siguiente se muestran las tareas que quizá desee llevar a cabo y la manera mejor de reemplazar los métodos de teclado.  Para obtener más información sobre los métodos de invalidación, vea [NOT IN BUILD: Overriding Properties and Methods](http://msdn.microsoft.com/es-es/2167e8f5-1225-4b13-9ebd-02591ba90213).  
  
|Tarea|Método|  
|-----------|------------|  
|Intercepte una tecla de navegación y genere un evento <xref:System.Windows.Forms.Control.KeyDown>.  Por ejemplo, desea controlar las teclas TAB y Retorno en un cuadro de texto.|Reemplace <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Note:**  Como alternativa, puede controlar el evento <xref:System.Windows.Forms.Control.PreviewKeyDown> y establecer la propiedad <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> de <xref:System.Windows.Forms.PreviewKeyDownEventArgs> en `true` para la tecla o las teclas que desee.|  
|Proporcione datos especiales o el control de navegación en un control.  Por ejemplo, desea que el uso de las teclas de dirección en el control de lista cambie el elemento seleccionado.|Reemplace <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|  
|Intercepte una tecla de navegación y genere un evento <xref:System.Windows.Forms.Control.KeyPress>.  Por ejemplo, en un control de cuadro de número desea que al presionar varias veces una tecla de dirección se acelere la progresión por los elementos.|Reemplace <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Proporcione datos especiales o el control de navegación durante un evento <xref:System.Windows.Forms.Control.KeyPress>.  Por ejemplo, en un control de lista si se mantiene presionada la tecla "r" se desplazará entre elementos que comienzan con la letra r.|Reemplace <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|  
|Realice un control de tecla de acceso personalizado; por ejemplo, desea controlar las teclas de acceso en botones dibujados por el propietario contenidos en una barra de herramientas.|Reemplace <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## Vea también  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.WndProc%2A>   
 <xref:System.Windows.Forms.Control.PreProcessMessage%2A>   
 [My.Computer.Keyboard \(Objeto\)](../../../ocs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)   
 [Acceso al teclado](../Topic/Accessing%20the%20Keyboard%20\(Visual%20Basic\).md)   
 [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md)