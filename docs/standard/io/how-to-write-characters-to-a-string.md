---
title: Procedimiento Escribir caracteres en una cadena
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: 21661a858cff9fc8bc84d497b4af8bedb1393f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734535"
---
# <a name="how-to-write-characters-to-a-string"></a>Procedimiento Escribir caracteres en una cadena

Los siguientes ejemplos de código escriben caracteres de forma sincrónica y asincrónica desde una matriz de caracteres en una cadena.  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a>Ejemplo: Escribir caracteres de forma sincrónica en una aplicación de consola  

 En el siguiente ejemplo se usa un <xref:System.IO.StringWriter> para escribir cinco caracteres de forma sincrónica en un objeto <xref:System.Text.StringBuilder>.
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a>Ejemplo: Escribir caracteres de forma asincrónica en una aplicación WPF

 El ejemplo siguiente es el código subyacente en una aplicación WPF. En la carga de la ventana, el ejemplo lee todos los caracteres de forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y los almacena en una matriz. Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente de un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [E/S de archivos y secuencias](index.md)  
- [E/S de archivos asincrónica](asynchronous-file-i-o.md)  
- [Cómo: Enumerar directorios y archivos](how-to-enumerate-directories-and-files.md)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](how-to-read-characters-from-a-string.md)
