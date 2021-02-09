---
description: 'Más información acerca de: Almacenar y leer datos en el Portapapeles (Visual Basic)'
title: Almacenamiento y lectura de datos en el Portapapeles
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 18cb66f6d8093757ce34ddb20659824787460920
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666347"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="50143-103">Almacenar y leer datos en el Portapapeles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50143-103">Storing data to and reading from the Clipboard (Visual Basic)</span></span>

<span data-ttu-id="50143-104">El Portapapeles se puede usar para almacenar datos, como texto e imágenes.</span><span class="sxs-lookup"><span data-stu-id="50143-104">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="50143-105">Dado que todos los procesos activos comparten el Portapapeles, se puede usar para transferir datos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="50143-105">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="50143-106">El objeto `My.Computer.Clipboard` permite acceder fácilmente al Portapapeles y leer y escribir en él.</span><span class="sxs-lookup"><span data-stu-id="50143-106">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="50143-107">Leer desde el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="50143-107">Reading from the Clipboard</span></span>  

 <span data-ttu-id="50143-108">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-108">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="50143-109">El código siguiente lee el texto y lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="50143-109">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="50143-110">Para que el ejemplo se ejecute correctamente debe haber texto almacenado en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-110">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 <span data-ttu-id="50143-111">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="50143-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="50143-112">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="50143-112">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="50143-113">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="50143-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="50143-114">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-114">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="50143-115">En este ejemplo se comprueba si hay una imagen en el Portapapeles antes de recuperarla y asignarla a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="50143-115">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 <span data-ttu-id="50143-116">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="50143-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="50143-117">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="50143-117">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="50143-118">Los elementos colocados en el Portapapeles se conservan incluso después de que se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50143-118">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="50143-119">Determinar el tipo de archivo almacenado en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="50143-119">Determining the type of file stored in the Clipboard</span></span>  

 <span data-ttu-id="50143-120">Los datos del Portapapeles pueden adoptar varios formatos distintos, como texto, un archivo de audio o una imagen.</span><span class="sxs-lookup"><span data-stu-id="50143-120">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="50143-121">Para determinar qué tipo de archivo está en el Portapapeles, puede usar métodos como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="50143-121">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="50143-122">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> puede usarse si tiene un formato personalizado que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="50143-122">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="50143-123">Use la función `ContainsImage` para determinar si los datos incluidos en el Portapapeles son una imagen.</span><span class="sxs-lookup"><span data-stu-id="50143-123">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="50143-124">El código siguiente comprueba si los datos son una imagen e informa en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="50143-124">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="50143-125">Borrar el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="50143-125">Clearing the Clipboard</span></span>  

 <span data-ttu-id="50143-126">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-126">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="50143-127">Dado que otros procesos comparten el Portapapeles, borrarlo puede afectar a esos procesos.</span><span class="sxs-lookup"><span data-stu-id="50143-127">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="50143-128">En el código siguiente se muestra cómo puede utilizar el método `Clear`.</span><span class="sxs-lookup"><span data-stu-id="50143-128">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="50143-129">Escribir en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="50143-129">Writing to the Clipboard</span></span>  

 <span data-ttu-id="50143-130">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-130">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="50143-131">El código siguiente escribe la cadena "This is a test string" en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-131">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 <span data-ttu-id="50143-132">El método `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="50143-132">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="50143-133">El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.</span><span class="sxs-lookup"><span data-stu-id="50143-133">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 <span data-ttu-id="50143-134">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-134">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="50143-135">Este ejemplo escribe `DataObject` `dataChunk` en el Portapapeles en el formato personalizado `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="50143-135">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 <span data-ttu-id="50143-136">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de audio en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-136">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="50143-137">Este ejemplo crea la matriz de bytes `musicReader`, lee el archivo `cool.wav` que hay dentro y lo escribe en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="50143-137">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> <span data-ttu-id="50143-138">Dado que otros usuarios pueden acceder al Portapapeles, no lo use para almacenar información confidencial, como contraseñas o datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="50143-138">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50143-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="50143-139">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [<span data-ttu-id="50143-140">Cómo: Leer datos de objetos en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="50143-140">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="50143-141">Cómo: Escribir datos de objeto en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="50143-141">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
