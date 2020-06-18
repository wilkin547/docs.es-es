---
title: 'Cómo: abrir archivos con el componente OpenFileDialog'
ms.date: 02/11/2019
description: Obtenga información sobre cómo usar el componente OpenFileDialog para abrir el cuadro de diálogo de Windows para examinar y seleccionar archivos.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904434"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Cómo: abrir archivos con el método OpenFileDialog

El <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente abre el cuadro de diálogo de Windows para examinar y seleccionar archivos. Para abrir y leer los archivos seleccionados, puede usar el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> método o crear una instancia de la <xref:System.IO.StreamReader?displayProperty=nameWithType> clase. En los ejemplos siguientes se muestran ambos enfoques.

En .NET Framework, para obtener o establecer la <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad se requiere un nivel de privilegios concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase. Los ejemplos ejecutan una <xref:System.Security.Permissions.FileIOPermission> comprobación de permisos y pueden producir una excepción debido a privilegios insuficientes si se ejecutan en un contexto de confianza parcial. Para obtener más información, vea [conceptos básicos](../../misc/code-access-security-basics.md)de la seguridad de acceso del código.

Puede compilar y ejecutar estos ejemplos como aplicaciones .NET Framework desde la línea de comandos de C# o Visual Basic. Para obtener más información, vea [compilar mediante línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partir de .NET Core 3,0, también puede compilar y ejecutar los ejemplos como aplicaciones Windows .NET Core desde una carpeta que tiene un archivo de proyecto Windows Forms * \<folder name> . csproj* de .net Core.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Ejemplo: leer un archivo como una secuencia con StreamReader  
  
En el ejemplo siguiente se usa el <xref:System.Windows.Forms.Button> controlador de eventos del control Windows Forms <xref:System.Windows.Forms.Control.Click> para abrir <xref:System.Windows.Forms.OpenFileDialog> con el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método. Una vez que el usuario elige un archivo y selecciona **Aceptar**, una instancia de la <xref:System.IO.StreamReader> clase lee el archivo y muestra su contenido en el cuadro de texto del formulario. Para obtener más información acerca de la lectura de secuencias de archivos, vea <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> y <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Ejemplo: abrir un archivo de una selección filtrada con OpenFile

En el ejemplo siguiente se usa el <xref:System.Windows.Forms.Button> controlador de eventos del control <xref:System.Windows.Forms.Control.Click> para abrir el <xref:System.Windows.Forms.OpenFileDialog> con un filtro que muestra solo archivos de texto. Una vez que el usuario elige un archivo de texto y selecciona **Aceptar**, el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método se usa para abrir el archivo en el Bloc de notas.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog (componente)](openfiledialog-component-windows-forms.md)
