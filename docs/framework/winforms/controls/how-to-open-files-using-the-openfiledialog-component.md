---
title: 'Cómo: Abrir archivos con el componente OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182132"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Cómo: Abrir archivos con OpenFileDialog

El <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente abre el cuadro de diálogo de Windows para examinar y seleccionar archivos. Para abrir y leer los archivos <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> seleccionados, puede utilizar <xref:System.IO.StreamReader?displayProperty=nameWithType> el método o crear una instancia de la clase. En los ejemplos siguientes se muestran ambos enfoques.

En .NET Framework, para <xref:System.Windows.Forms.FileDialog.FileName%2A> obtener o establecer la propiedad <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> se requiere un nivel de privilegio concedido por la clase. Los ejemplos <xref:System.Security.Permissions.FileIOPermission> ejecutan una comprobación de permisos y pueden producir una excepción debido a privilegios insuficientes si se ejecutan en un contexto de confianza parcial. Para obtener más información, consulte [Conceptos básicos](../../misc/code-access-security-basics.md)de seguridad de acceso a código .

Puede compilar y ejecutar estos ejemplos como aplicaciones de .NET Framework desde la línea de comandos de Visual Basic o de C. Para obtener más información, vea [Creación de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o Compilación desde la línea de [comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partir de .NET Core 3.0, también puede compilar y ejecutar los ejemplos como aplicaciones de Windows .NET Core desde una carpeta que tiene un nombre de * \<carpeta* de formularios Windows Forms de .NET Core> archivo de proyecto.csproj.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Ejemplo: Leer un archivo como una secuencia con StreamReader  
  
En <xref:System.Windows.Forms.Button> el <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ejemplo siguiente se usa el controlador <xref:System.Windows.Forms.OpenFileDialog> de eventos del control de formularios Windows Forms para abrir el método. Después de que el usuario **OK**elige un archivo <xref:System.IO.StreamReader> y selecciona Aceptar , una instancia de la clase lee el archivo y muestra su contenido en el cuadro de texto del formulario. Para obtener más información acerca de <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>la lectura de secuencias de archivos, consulte y .  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Ejemplo: Abra un archivo desde una selección filtrada con OpenFile

En el ejemplo <xref:System.Windows.Forms.Button> siguiente <xref:System.Windows.Forms.Control.Click> se usa el <xref:System.Windows.Forms.OpenFileDialog> controlador de eventos del control para abrir el con un filtro que muestra solo los archivos de texto. Después de que el usuario **OK**elige un <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> archivo de texto y selecciona Aceptar , el método se utiliza para abrir el archivo en el Bloc de notas.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
