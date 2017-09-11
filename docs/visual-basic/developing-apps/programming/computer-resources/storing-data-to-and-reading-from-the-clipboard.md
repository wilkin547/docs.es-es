---
title: Almacenar y leer datos en el Portapapeles (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3b60942cf3e3a7f588a7838bcae0cb7b6fae2278
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="23510-102">Almacenar y leer datos en el Portapapeles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23510-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="23510-103">El Portapapeles se puede usar para almacenar datos, como texto e imágenes.</span><span class="sxs-lookup"><span data-stu-id="23510-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="23510-104">Dado que todos los procesos activos comparten el Portapapeles, se puede usar para transferir datos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="23510-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="23510-105">El objeto `My.Computer.Clipboard` permite acceder fácilmente al Portapapeles y leer y escribir en él.</span><span class="sxs-lookup"><span data-stu-id="23510-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="23510-106">Leer desde el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="23510-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="23510-107">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="23510-108">El código siguiente lee el texto y lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="23510-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="23510-109">Para que el ejemplo se ejecute correctamente debe haber texto almacenado en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 <span data-ttu-id="23510-110">[!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-110">[!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]</span></span>  
  
 <span data-ttu-id="23510-111">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="23510-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="23510-112">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="23510-112">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="23510-113">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="23510-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="23510-114">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-114">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="23510-115">En este ejemplo se comprueba si hay una imagen en el Portapapeles antes de recuperarla y asignarla a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="23510-115">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 <span data-ttu-id="23510-116">[!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-116">[!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]</span></span>  
  
 <span data-ttu-id="23510-117">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="23510-117">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="23510-118">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="23510-118">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="23510-119">Los elementos colocados en el Portapapeles se conservan incluso después de que se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23510-119">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="23510-120">Determinar el tipo de archivo almacenado en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="23510-120">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="23510-121">Los datos del Portapapeles pueden adoptar varios formatos distintos, como texto, un archivo de audio o una imagen.</span><span class="sxs-lookup"><span data-stu-id="23510-121">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="23510-122">Para determinar qué tipo de archivo está en el Portapapeles, puede usar métodos como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="23510-122">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="23510-123">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> puede usarse si tiene un formato personalizado que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="23510-123">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="23510-124">Use la función `ContainsImage` para determinar si los datos incluidos en el Portapapeles son una imagen.</span><span class="sxs-lookup"><span data-stu-id="23510-124">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="23510-125">El código siguiente comprueba si los datos son una imagen e informa en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="23510-125">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 <span data-ttu-id="23510-126">[!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-126">[!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]</span></span>  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="23510-127">Borrar el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="23510-127">Clearing the Clipboard</span></span>  
 <span data-ttu-id="23510-128">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-128">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="23510-129">Dado que otros procesos comparten el Portapapeles, borrarlo puede afectar a esos procesos.</span><span class="sxs-lookup"><span data-stu-id="23510-129">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="23510-130">En el código siguiente se muestra cómo puede utilizar el método `Clear`.</span><span class="sxs-lookup"><span data-stu-id="23510-130">The following code shows how to use the `Clear` method.</span></span>  
  
 <span data-ttu-id="23510-131">[!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-131">[!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]</span></span>  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="23510-132">Escribir en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="23510-132">Writing to the Clipboard</span></span>  
 <span data-ttu-id="23510-133">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="23510-134">El código siguiente escribe la cadena "This is a test string" en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-134">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 <span data-ttu-id="23510-135">[!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-135">[!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]</span></span>  
  
 <span data-ttu-id="23510-136">El método `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="23510-136">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="23510-137">El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.</span><span class="sxs-lookup"><span data-stu-id="23510-137">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 <span data-ttu-id="23510-138">[!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-138">[!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]</span></span>  
  
 <span data-ttu-id="23510-139">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-139">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="23510-140">Este ejemplo escribe `DataObject``dataChunk` en el Portapapeles en el formato personalizado `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="23510-140">This example writes the `DataObject``dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 <span data-ttu-id="23510-141">[!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-141">[!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]</span></span>  
  
 <span data-ttu-id="23510-142">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de audio en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-142">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="23510-143">Este ejemplo crea la matriz de bytes `musicReader`, lee el archivo `cool.wav` que hay dentro y lo escribe en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="23510-143">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 <span data-ttu-id="23510-144">[!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="23510-144">[!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23510-145">Dado que otros usuarios pueden acceder al Portapapeles, no lo use para almacenar información confidencial, como contraseñas o datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="23510-145">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23510-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="23510-146">See also</span></span>  
 <span data-ttu-id="23510-147"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy></span><span class="sxs-lookup"><span data-stu-id="23510-147"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy></span></span>   
 <span data-ttu-id="23510-148"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A></span><span class="sxs-lookup"><span data-stu-id="23510-148"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A></span></span>   
 <span data-ttu-id="23510-149"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A></span><span class="sxs-lookup"><span data-stu-id="23510-149"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A></span></span>   
 <span data-ttu-id="23510-150">[How to: Read Object Data from an XML File (Cómo: Leer datos de objetos de un archivo XML)](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="23510-150">[How to: Read Object Data from an XML File](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
 [<span data-ttu-id="23510-151">Escribir objetos de datos en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="23510-151">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)

