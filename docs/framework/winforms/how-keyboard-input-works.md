---
title: Funcionamiento de las entradas mediante teclado
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: 369c434f5443334ccb8b136ce50ff2d5db8ece01
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963445"
---
# <a name="how-keyboard-input-works"></a>Funcionamiento de las entradas mediante teclado
Los Windows Forms procesan las entradas mediante teclado provocando eventos de teclado en respuesta a los mensajes de Windows. La mayoría de las aplicaciones de Windows Forms procesan exclusivamente las entradas mediante teclado controlando los eventos de teclado. No obstante, es necesario comprender cómo funcionan los mensajes del teclado de modo que pueda implementar escenarios de entrada mediante teclado más avanzados, como interceptar teclas antes de que lleguen a un control. En este tema se describen los tipos de datos de tecla que los Windows Forms reconocen y se proporciona información general de cómo se enrutan los mensajes del teclado. Para información sobre los eventos de teclado, vea [Utilizar eventos de teclado](using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Tipos de teclas  
 Windows Forms identifica la entrada del teclado como códigos de tecla virtual que están representados por la enumeración bit a bit <xref:System.Windows.Forms.Keys> . Con la <xref:System.Windows.Forms.Keys> enumeración, puede combinar una serie de teclas presionadas para generar un valor único. Estos valores corresponden a los valores que acompañan a los mensajes de Windows WM_KEYDOWN y WM_SYSKEYDOWN. Puede detectar la mayoría de las pulsaciones de tecla <xref:System.Windows.Forms.Control.KeyDown> físicas <xref:System.Windows.Forms.Control.KeyUp> controlando los eventos o. Las claves de caracteres son un subconjunto de la <xref:System.Windows.Forms.Keys> enumeración y se corresponden con los valores que acompañan a los mensajes de Windows WM_CHAR y WM_SYSCHAR. Si la combinación de teclas presionadas da como resultado un carácter, puede detectar el carácter controlando <xref:System.Windows.Forms.Control.KeyPress> el evento. Como alternativa, puede usar <xref:Microsoft.VisualBasic.Devices.Keyboard>, expuesto por Visual Basic interfaz de programación, para detectar qué teclas se presionaron y enviar las claves. Para más información, consulte [Acceso al teclado](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).  
  
## <a name="order-of-keyboard-events"></a>Orden de eventos de teclado  
 Como se ha indicado anteriormente, hay 3 eventos relacionados con el teclado que pueden ocurrir en un control. La secuencia siguiente muestra el orden general de los eventos:  
  
1. El usuario presiona la tecla "a", la clave se preprocesa, se envía y se produce un <xref:System.Windows.Forms.Control.KeyDown> evento.  
  
2. El usuario mantiene presionada la tecla "a", la clave se preprocesa, se envía y se produce <xref:System.Windows.Forms.Control.KeyPress> un evento.  
  
     Este evento se produce varias veces cuando el usuario mantiene presionada una tecla.  
  
3. El usuario suelta la tecla "a", la clave se preprocesa, se envía y se produce un <xref:System.Windows.Forms.Control.KeyUp> evento.  
  
## <a name="preprocessing-keys"></a>Preprocesamiento de teclas  
 Al igual que otros mensajes, los mensajes del teclado <xref:System.Windows.Forms.Control.WndProc%2A> se procesan en el método de un formulario o un control. Sin embargo, antes de que se procesen los mensajes del teclado, el <xref:System.Windows.Forms.Control.PreProcessMessage%2A> método llama a uno o varios métodos que se pueden invalidar para controlar teclas de caracteres especiales y teclas físicas. Puede reemplazar estos métodos para detectar y filtrar determinadas teclas antes de que el control procese los mensajes. En la tabla siguiente se muestra la acción que se realiza y el método relacionado que se produce, en el orden en que se produce el método.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Preprocesamiento de un evento KeyDown  
  
|.|Método relacionado|Notas|  
|------------|--------------------|-----------|  
|Comprobar si es una tecla de comando como un acelerador o un método abreviado de menú.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Este método procesa una tecla de comando, que tiene prioridad sobre las teclas normales. Si este método devuelve `true`, no se envía el mensaje de tecla y no se produce un evento de clave. Si devuelve `false`, <xref:System.Windows.Forms.Control.IsInputKey%2A> se llama a.`.`|  
|Compruebe si hay una tecla especial que requiera preprocesamiento o una tecla de carácter normal que deba <xref:System.Windows.Forms.Control.KeyDown> generar un evento y que se envíe a un control.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Si el método devuelve `true`, significa que el control es un carácter normal y se <xref:System.Windows.Forms.Control.KeyDown> genera un evento. Si `false`es <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> , se llama a. **Nota:**  Para asegurarse de que un control obtiene una tecla o combinación de teclas, puede controlar <xref:System.Windows.Forms.Control.PreviewKeyDown> el evento y <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> el conjunto <xref:System.Windows.Forms.PreviewKeyDownEventArgs> de `true` para las claves que desee.|  
|Comprobar si es una tecla de navegación (ESC, TAB, Retorno o teclas de flecha).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Este método procesa una clave física que emplea la funcionalidad especial dentro del control, como cambiar el foco entre el control y su elemento primario. Si el control inmediato no controla la clave, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> se llama a en el control principal y así sucesivamente al control de nivel superior de la jerarquía. Si este método devuelve `true`, finaliza el preprocesamiento y no se genera un evento de clave. Si devuelve `false`, se produce <xref:System.Windows.Forms.Control.KeyDown> un evento.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Preprocesamiento de un evento KeyPress  
  
|Acción|Método relacionado|Notas|  
|------------|--------------------|-----------|  
|Comprobar si la tecla es un carácter normal que el control debería procesar.|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Si el carácter es un carácter normal, este método devuelve `true`, se <xref:System.Windows.Forms.Control.KeyPress> genera el evento y no se produce ningún preprocesamiento adicional. De <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> lo contrario, se llamará a.|  
|Comprobar si el carácter es un código de tecla de acceso (como &Aceptar en un botón).|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Este método, similar a <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, se llamará en la jerarquía de controles. Si el control es un control contenedor, comprueba si hay teclas de método llamando <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> a en sí mismo y a sus controles secundarios. Si <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> <xref:System.Windows.Forms.Control.KeyPress> devuelve `true`, no se produce un evento.|  
  
## <a name="processing-keyboard-messages"></a>Procesamiento de mensajes del teclado  
 Una vez que los mensajes <xref:System.Windows.Forms.Control.WndProc%2A> del teclado alcanzan el método de un formulario o un control, los procesa un conjunto de métodos que se pueden invalidar. Cada uno de estos métodos devuelve <xref:System.Boolean> un valor que especifica si el control ha procesado y consumido el mensaje del teclado. Si uno de los métodos devuelve `true`, se considera que se ha controlado el mensaje y no se pasa al base o primario del control para más procesamiento. De lo contrario, el mensaje permanece en la cola de mensajes y se puede procesar en otro método en el elemento base o primario del control. En la tabla siguiente se presentan los métodos que procesan los mensajes del teclado.  
  
|Método|Notas|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Este método procesa todos los mensajes del teclado que recibe el <xref:System.Windows.Forms.Control.WndProc%2A> método del control.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Este método envía el mensaje del teclado al elemento primario del control. Si <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> devuelve `true`, no se genera ningún evento de clave; de lo contrario, se llama a.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Este método genera los <xref:System.Windows.Forms.Control.KeyDown>eventos <xref:System.Windows.Forms.Control.KeyPress>, y <xref:System.Windows.Forms.Control.KeyUp> , según corresponda.|  
  
## <a name="overriding-keyboard-methods"></a>Invalidación de métodos de teclado  
 Hay muchos métodos disponibles de invalidación cuando se preprocesa y procesa un mensaje del teclado; sin embargo, algunos métodos son opciones mucho mejores que otros. En la tabla siguiente se muestran las tareas que quizá desee llevar a cabo y la mejor forma de invalidar los métodos de teclado. Para obtener más información sobre los métodos de invalidación, vea [invalidar propiedades y métodos en clases derivadas](../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes).  
  
|Tarea|Método|  
|----------|------------|  
|Interceptar una tecla de navegación y <xref:System.Windows.Forms.Control.KeyDown> generar un evento. Por ejemplo, desea controlar las teclas TAB y Retorno en un cuadro de texto.|Reemplace <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Nota:**  Como alternativa, puede controlar <xref:System.Windows.Forms.Control.PreviewKeyDown> el evento y el conjunto <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> de <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` para las claves que desee.|  
|Realice entradas especiales o ejecute el control de navegación en un control. Por ejemplo, desea que el uso de las teclas de flecha en el control de lista cambie el elemento seleccionado.|Invalide <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|  
|Interceptar una tecla de navegación y <xref:System.Windows.Forms.Control.KeyPress> generar un evento. Por ejemplo, en un control de cuadro de número desea que al presionar varias veces una tecla de flecha se acelere la progresión por los elementos.|Reemplace <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Realizar un control de entrada o navegación especial <xref:System.Windows.Forms.Control.KeyPress> durante un evento. Por ejemplo, en un control de lista, si se mantiene presionada la tecla "r", se desplazará entre elementos que comienzan con la letra r.|Invalide <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|  
|Realice un control de tecla de acceso personalizado; por ejemplo, desea controlar las teclas de acceso en botones dibujados por el propietario contenidos en una barra de herramientas.|Reemplace <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [My.Computer.Keyboard (objeto)](../../visual-basic/language-reference/objects/my-computer-keyboard-object.md)
- [Acceso al teclado](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)
- [Utilizar eventos de teclado](using-keyboard-events.md)
