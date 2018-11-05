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
ms.openlocfilehash: 9c637d9842c05f47bfcaa0431dd2f9f1ee29cc09
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50181243"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="a8f71-102">Cómo: Escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="a8f71-102">How to: Write Text to a File</span></span>
<span data-ttu-id="a8f71-103">En este tema se describen diferentes formas de escribir texto en un archivo para aplicaciones de .NET Framework o aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8f71-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="a8f71-104">Las clases y los métodos siguientes normalmente se usan para escribir texto en un archivo:</span><span class="sxs-lookup"><span data-stu-id="a8f71-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="a8f71-105"><xref:System.IO.StreamWriter> : contiene métodos para escribir en un archivo de forma sincrónica (<xref:System.IO.StreamWriter.Write%2A> o <xref:System.IO.TextWriter.WriteLine%2A>) o asincrónica (<xref:System.IO.StreamWriter.WriteAsync%2A> y <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="a8f71-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="a8f71-106"><xref:System.IO.File> : para usar con aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8f71-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="a8f71-107">Proporciona métodos estáticos para escribir texto en un archivo (por ejemplo, <xref:System.IO.File.WriteAllLines%2A> y <xref:System.IO.File.WriteAllText%2A>) o para anexar texto a un archivo (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> o <xref:System.IO.File.AppendText%2A>).</span><span class="sxs-lookup"><span data-stu-id="a8f71-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="a8f71-108"><xref:Windows.Storage.FileIO>: para usar con aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8f71-108"><xref:Windows.Storage.FileIO> - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="a8f71-109">Contiene métodos asincrónicos para escribir texto en un archivo (<xref:Windows.Storage.FileIO.WriteLinesAsync%2A> y <xref:Windows.Storage.FileIO.WriteTextAsync%2A>) o para anexar texto a un archivo (<xref:Windows.Storage.FileIO.AppendLinesAsync%2A> o <xref:Windows.Storage.FileIO.AppendTextAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="a8f71-109">It contains asynchronous methods to write text to a file (<xref:Windows.Storage.FileIO.WriteLinesAsync%2A> or <xref:Windows.Storage.FileIO.WriteTextAsync%2A>) or to append text to a file (<xref:Windows.Storage.FileIO.AppendLinesAsync%2A> or <xref:Windows.Storage.FileIO.AppendTextAsync%2A>).</span></span>  

- <span data-ttu-id="a8f71-110"><xref:System.IO.Path> se usa en cadenas que contienen información de la ruta de acceso al archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="a8f71-110"><xref:System.IO.Path> - to be used on strings that contain file or directory path information.</span></span> <span data-ttu-id="a8f71-111">Contiene el método <xref:System.IO.Path.Combine%2A>, que permite la concatenación de cadenas para compilar una ruta de acceso al archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="a8f71-111">It contains the <xref:System.IO.Path.Combine%2A> method, which allows concatenation of strings to build a file or directory path.</span></span>


 <span data-ttu-id="a8f71-112">Presentamos ejemplos sencillos para permitirle centrarse en la tarea que esté realizando.</span><span class="sxs-lookup"><span data-stu-id="a8f71-112">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="a8f71-113">Por este motivo, en los ejemplos se realizan una comprobación de errores y un control de excepciones mínimos, si hubiera.</span><span class="sxs-lookup"><span data-stu-id="a8f71-113">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="a8f71-114">Generalmente, una aplicación real ofrece una comprobación de errores y un control de excepciones más exhaustivos.</span><span class="sxs-lookup"><span data-stu-id="a8f71-114">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8f71-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f71-115">Example</span></span>  
 <span data-ttu-id="a8f71-116">En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma sincrónica mediante la clase <xref:System.IO.StreamWriter> , una línea a la vez.</span><span class="sxs-lookup"><span data-stu-id="a8f71-116">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="a8f71-117">El nuevo archivo de texto se guarda en la carpeta Mis documentos del usuario.</span><span class="sxs-lookup"><span data-stu-id="a8f71-117">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="a8f71-118">Dado que en la instrucción <xref:System.IO.StreamWriter> se declara el objeto `using` y se crea una instancia de este, se invoca el método <xref:System.IO.StreamWriter.Dispose%2A> que automáticamente vacía y cierra el flujo.</span><span class="sxs-lookup"><span data-stu-id="a8f71-118">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="a8f71-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f71-119">Example</span></span>  
 <span data-ttu-id="a8f71-120">En el ejemplo siguiente se muestra cómo anexar texto a un archivo existente mediante la clase <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="a8f71-120">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="a8f71-121">Se usa el mismo archivo de texto del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a8f71-121">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="a8f71-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f71-122">Example</span></span>  
 <span data-ttu-id="a8f71-123">En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma asincrónica mediante la clase <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="a8f71-123">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="a8f71-124">Para invocar el método <xref:System.IO.StreamWriter.WriteAsync%2A> , la llamada al método debe estar dentro de un método `async` .</span><span class="sxs-lookup"><span data-stu-id="a8f71-124">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="a8f71-125">El nuevo archivo de texto se guarda en la carpeta Mis documentos del usuario.</span><span class="sxs-lookup"><span data-stu-id="a8f71-125">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="a8f71-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f71-126">Example</span></span>  
 <span data-ttu-id="a8f71-127">En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo y anexar nuevas líneas de texto en el mismo archivo con la clase <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="a8f71-127">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="a8f71-128">Los métodos <xref:System.IO.File.WriteAllText%2A> y <xref:System.IO.File.AppendAllLines%2A> abren y cierran el archivo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a8f71-128">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="a8f71-129">Si ya existe la ruta de acceso al método <xref:System.IO.File.WriteAllText%2A> proporcionada, se sobrescribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="a8f71-129">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="a8f71-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f71-130">Example</span></span>  
 <span data-ttu-id="a8f71-131">En el siguiente ejemplo se muestra cómo escribir asincrónicamente en un archivo de texto los datos proporcionados por el usuario en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8f71-131">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="a8f71-132">Por cuestiones de seguridad, la apertura de un archivo desde una aplicación de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] normalmente requiere el uso de un control <xref:Windows.Storage.Pickers.FileOpenPicker>.</span><span class="sxs-lookup"><span data-stu-id="a8f71-132">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a <xref:Windows.Storage.Pickers.FileOpenPicker> control.</span></span> <span data-ttu-id="a8f71-133">En este ejemplo, `FileOpenPicker` se filtra para mostrar archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="a8f71-133">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8f71-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8f71-134">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.Path>  
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="a8f71-135">Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="a8f71-135">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="a8f71-136">Cómo: Leer y escribir en un archivo de datos recién creado</span><span class="sxs-lookup"><span data-stu-id="a8f71-136">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="a8f71-137">Cómo: Abrir y anexar a un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="a8f71-137">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="a8f71-138">Cómo: Leer texto de un archivo</span><span class="sxs-lookup"><span data-stu-id="a8f71-138">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="a8f71-139">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="a8f71-139">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
