---
title: Procedimiento para cargar un sonido de forma asincrónica en un formulario Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 1d710f1e6d3b208365d5b1eb2524fbeeaa673c2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941055"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a>Procedimiento para cargar un sonido de forma asincrónica en un formulario Windows Forms
En el ejemplo de código siguiente, se carga un sonido de forma asincrónica desde una dirección URL y, a continuación, se reproduce en un nuevo subproceso.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System y System.Windows.Forms.  
  
- Que reemplace el nombre de archivo `"http://www.tailspintoys.com/sounds/stop.wav"` por un nombre de archivo válido.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
- El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco (clase <xref:System.ArgumentException>).  
  
- La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).  
  
- El nombre de la ruta de acceso es `Nothing` (clase <xref:System.ArgumentNullException>).  
  
- El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).  
  
- La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).  
  
- La ruta de acceso es solo dos puntos ":" (clase <xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [Cómo: Reproducir un sonido desde Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
