---
title: 'Cómo: Mostrar los puertos serie disponibles'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: b19bdd56311ab7029fb224256d138a0dc0dd8ddc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557351"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Cómo: Mostrar los puertos serie disponibles en Visual Basic

En este tema se explica cómo usar `My.Computer.Ports` para mostrar los puertos serie disponibles del equipo en Visual Basic.  
  
 Para permitir al usuario seleccionar qué puerto quiere usar, los nombres de los puertos serie se colocan en un control <xref:System.Windows.Forms.ListBox>.  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo recorre todas las cadenas que devuelve la propiedad `My.Computer.Ports.SerialPortNames`. Estas cadenas son los nombres de los puertos serie disponibles en el equipo.  
  
 Normalmente, los usuarios seleccionan el puerto serie que la aplicación debe usar en la lista de puertos disponibles. En este ejemplo, los nombres de los puertos serie se almacenan en un control <xref:System.Windows.Forms.ListBox>. Para obtener más información, consulte [ListBox Control](/dotnet/desktop/winforms/controls/listbox-control-windows-forms) (Control ListBox).  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Conectividad y redes**. Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Una referencia de proyecto a System.Windows.Forms.dll.  
  
- Acceso a los miembros del espacio de nombres <xref:System.Windows.Forms>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
- Que su formulario tenga un control <xref:System.Windows.Forms.ListBox> denominado `ListBox1`.  
  
## <a name="robust-programming"></a>Programación sólida  

 No resulta necesario usar el control <xref:System.Windows.Forms.ListBox> para mostrar los nombres de los puertos serie disponibles. En su lugar, puede usar un <xref:System.Windows.Forms.ComboBox> u otro control. Si la aplicación no necesita una respuesta del usuario, puede usar un control <xref:System.Windows.Forms.TextBox> para mostrar la información.  
  
> [!NOTE]
> Los nombres de puerto devueltos por `My.Computer.Ports.SerialPortNames` pueden ser incorrectos cuando la ejecución se realiza en Windows 98. Para evitar errores de aplicación, use el control de excepciones, como las instrucciones `Try...Catch...Finally` o `Using`, al usar los nombres de puerto para abrir puertos.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Marcar a través de módems conectados a puertos serie](how-to-dial-modems-attached-to-serial-ports.md)
- [Enviar cadenas a puertos serie](how-to-send-strings-to-serial-ports.md)
- [Recibir cadenas de puertos serie](how-to-receive-strings-from-serial-ports.md)
