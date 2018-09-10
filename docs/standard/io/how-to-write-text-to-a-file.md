---
title: 'Cómo: Escribir texto en un archivo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc8082175047271c92f9a9a17a49534ffc9546a9
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270820"
---
# <a name="how-to-write-text-to-a-file"></a>Cómo: Escribir texto en un archivo
En este tema se describen diferentes formas de escribir texto en un archivo para aplicaciones de .NET Framework o aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Las clases y los métodos siguientes normalmente se usan para escribir texto en un archivo:  
  
-   <xref:System.IO.StreamWriter>: contiene métodos para escribir en un archivo de forma sincrónica (<xref:System.IO.StreamWriter.Write%2A> o <xref:System.IO.TextWriter.WriteLine%2A>) o asincrónica (<xref:System.IO.StreamWriter.WriteAsync%2A> y <xref:System.IO.StreamWriter.WriteLineAsync%2A>).  
  
-   <xref:System.IO.File>: para usar con aplicaciones de .NET Framework. Proporciona métodos estáticos para escribir texto en un archivo (por ejemplo, <xref:System.IO.File.WriteAllLines%2A> y <xref:System.IO.File.WriteAllText%2A>) o para anexar texto a un archivo (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> o <xref:System.IO.File.AppendText%2A>).  
  
-   [FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) : para usar con aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] . Contiene métodos asincrónicos para escribir texto en un archivo ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) o [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) o anexar texto a un archivo ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) o [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).  

- <xref:System.IO.Path> se usa en cadenas que contienen información de la ruta de acceso al archivo o directorio. Contiene el método <xref:System.IO.Path.Combine%2A>, que permite la concatenación de cadenas para compilar una ruta de acceso al archivo o directorio.


 Presentamos ejemplos sencillos para permitirle centrarse en la tarea que esté realizando. Por este motivo, en los ejemplos se realizan una comprobación de errores y un control de excepciones mínimos, si hubiera. Generalmente, una aplicación real ofrece una comprobación de errores y un control de excepciones más exhaustivos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma sincrónica mediante la clase <xref:System.IO.StreamWriter>, una línea a la vez. El nuevo archivo de texto se guarda en la carpeta Mis documentos del usuario. Dado que en la instrucción `using` se declara el objeto <xref:System.IO.StreamWriter> y se crea una instancia de este, se invoca el método <xref:System.IO.StreamWriter.Dispose%2A> que automáticamente vacía y cierra el flujo.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo anexar texto a un archivo existente mediante la clase <xref:System.IO.StreamWriter>. Se usa el mismo archivo de texto del ejemplo anterior.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma asincrónica mediante la clase <xref:System.IO.StreamWriter>. Para invocar el método <xref:System.IO.StreamWriter.WriteAsync%2A>, la llamada al método debe estar dentro de un método `async`. El nuevo archivo de texto se guarda en la carpeta Mis documentos del usuario.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo y anexar nuevas líneas de texto en el mismo archivo con la clase <xref:System.IO.File>. Los métodos <xref:System.IO.File.WriteAllText%2A> y <xref:System.IO.File.AppendAllLines%2A> abren y cierran el archivo automáticamente. Si ya existe la ruta de acceso al método <xref:System.IO.File.WriteAllText%2A> proporcionada, se sobrescribe el archivo.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo escribir asincrónicamente en un archivo de texto los datos proporcionados por el usuario en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Por cuestiones de seguridad, la apertura de un archivo desde una aplicación de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] normalmente requiere el uso de un control [FileOpenPicker](https://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx). En este ejemplo, `FileOpenPicker` se filtra para mostrar archivos de texto.  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.Path>  
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
- [Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
