---
title: Filtrar Abrir archivos con el componente OpenFileDialog
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 5781543a61d77ef8f0658e95759c57fdb77cfc4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723093"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Procedimiento Archivos abiertos con OpenFileDialog 

El <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente abre el cuadro de diálogo de Windows para examinar y seleccionar los archivos. Para abrir y leer los archivos seleccionados, puede usar el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> método, o cree una instancia de la <xref:System.IO.StreamReader?displayProperty=nameWithType> clase. Los ejemplos siguientes muestran ambos enfoques. 

En .NET Framework, para obtener o establecer el <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase. Los ejemplos ejecutan una <xref:System.Security.Permissions.FileIOPermission> permiso comprobar y puede producir una excepción por falta de privilegios si se ejecuta en un contexto de confianza parcial. Para obtener más información, consulte [conceptos básicos sobre la seguridad de acceso de código](../../misc/code-access-security-basics.md).

Puede compilar y ejecutar estos ejemplos como aplicaciones de .NET Framework desde el C# o línea de comandos de Visual Basic. Para obtener más información, consulte [de línea de comandos para compilar con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [construido a partir de la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

A partir de .NET Core 3.0, también puede compilar y ejecutar los ejemplos como aplicaciones de .NET Core de Windows desde una carpeta que tenga un núcleo de .NET Windows Forms  *\<nombre de carpeta > .csproj* archivo de proyecto. 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Ejemplo: Leer un archivo como una secuencia con StreamReader  
  
El ejemplo siguiente utiliza los formularios de Windows <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos para abrir el <xref:System.Windows.Forms.OpenFileDialog> con el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método. Después de que el usuario elige un archivo y selecciona **Aceptar**, una instancia de la <xref:System.IO.StreamReader> lee el archivo de clase y muestra su contenido en el cuadro de texto del formulario. Para obtener más información sobre la lectura de secuencias de archivo, consulte <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> y <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Ejemplo: Abrir un archivo de una selección con OpenFile filtrada 

En el ejemplo siguiente se usa el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos para abrir el <xref:System.Windows.Forms.OpenFileDialog> con un filtro que muestra sólo los archivos de texto. Después de que el usuario elige un archivo de texto y selecciona **Aceptar**, el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método se usa para abrir el archivo en el Bloc de notas.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog (componente)](openfiledialog-component-windows-forms.md)
