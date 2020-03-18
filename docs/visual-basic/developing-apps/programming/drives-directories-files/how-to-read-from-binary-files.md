---
title: 'Cómo: Leer archivos binarios'
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: c33bc72a5c79901e3715ed6a587ffdb8e3565e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335294"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a>Cómo: Leer archivos binarios en Visual Basic

El objeto `My.Computer.FileSystem` proporciona el método `ReadAllBytes` para leer archivos binarios.  
  
### <a name="to-read-from-a-binary-file"></a>Para leer un archivo binario  
  
- Use el método `ReadAllBytes`, que devuelve el contenido de un archivo como una matriz de bytes. En este ejemplo se lee el archivo `C:/Documents and Settings/selfportrait.jpg`.  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- Para los archivos binarios grandes, puede usar el método <xref:System.IO.FileStream.Read%2A> del objeto <xref:System.IO.FileStream> para leer solo una cantidad especificada del archivo a la vez. Después, puede limitar la cantidad de contenido del archivo que se carga en memoria para cada operación de lectura. En el ejemplo de código siguiente se copia un archivo y se permite al autor de la llamada especificar la cantidad de contenido del archivo que se lee en memoria por cada operación de lectura.  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar que se produzca una excepción:  
  
- La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- El archivo no existe (<xref:System.IO.FileNotFoundException>).  
  
- El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  
  
 Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Almacenar y leer datos en el Portapapeles](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
