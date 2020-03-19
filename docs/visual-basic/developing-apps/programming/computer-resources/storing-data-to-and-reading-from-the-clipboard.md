---
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
ms.openlocfilehash: 243fb237f3f9ba53f8b29079df08531c102c78dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349732"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="be57f-102">Almacenar y leer datos en el Portapapeles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be57f-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>

<span data-ttu-id="be57f-103">El Portapapeles se puede usar para almacenar datos, como texto e imágenes.</span><span class="sxs-lookup"><span data-stu-id="be57f-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="be57f-104">Dado que todos los procesos activos comparten el Portapapeles, se puede usar para transferir datos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="be57f-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="be57f-105">El objeto `My.Computer.Clipboard` permite acceder fácilmente al Portapapeles y leer y escribir en él.</span><span class="sxs-lookup"><span data-stu-id="be57f-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="be57f-106">Leer desde el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="be57f-106">Reading from the Clipboard</span></span>  

 <span data-ttu-id="be57f-107">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> para leer el texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="be57f-108">El código siguiente lee el texto y lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="be57f-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="be57f-109">Para que el ejemplo se ejecute correctamente debe haber texto almacenado en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 <span data-ttu-id="be57f-110">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="be57f-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="be57f-111">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="be57f-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="be57f-112">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="be57f-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="be57f-113">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> para recuperar una imagen del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="be57f-114">En este ejemplo se comprueba si hay una imagen en el Portapapeles antes de recuperarla y asignarla a `PictureBox1`.</span><span class="sxs-lookup"><span data-stu-id="be57f-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 <span data-ttu-id="be57f-115">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="be57f-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="be57f-116">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Portapapeles**. Para más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="be57f-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="be57f-117">Los elementos colocados en el Portapapeles se conservan incluso después de que se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be57f-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="be57f-118">Determinar el tipo de archivo almacenado en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="be57f-118">Determining the type of file stored in the Clipboard</span></span>  

 <span data-ttu-id="be57f-119">Los datos del Portapapeles pueden adoptar varios formatos distintos, como texto, un archivo de audio o una imagen.</span><span class="sxs-lookup"><span data-stu-id="be57f-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="be57f-120">Para determinar qué tipo de archivo está en el Portapapeles, puede usar métodos como <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> y <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span><span class="sxs-lookup"><span data-stu-id="be57f-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="be57f-121">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> puede usarse si tiene un formato personalizado que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="be57f-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="be57f-122">Use la función `ContainsImage` para determinar si los datos incluidos en el Portapapeles son una imagen.</span><span class="sxs-lookup"><span data-stu-id="be57f-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="be57f-123">El código siguiente comprueba si los datos son una imagen e informa en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="be57f-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="be57f-124">Borrar el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="be57f-124">Clearing the Clipboard</span></span>  

 <span data-ttu-id="be57f-125">El método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> borra el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="be57f-126">Dado que otros procesos comparten el Portapapeles, borrarlo puede afectar a esos procesos.</span><span class="sxs-lookup"><span data-stu-id="be57f-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="be57f-127">En el código siguiente se muestra cómo puede utilizar el método `Clear`.</span><span class="sxs-lookup"><span data-stu-id="be57f-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="be57f-128">Escribir en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="be57f-128">Writing to the Clipboard</span></span>  

 <span data-ttu-id="be57f-129">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> para escribir texto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="be57f-130">El código siguiente escribe la cadena "This is a test string" en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 <span data-ttu-id="be57f-131">El método `SetText` puede aceptar un parámetro de formato que contenga un tipo de <xref:System.Windows.Forms.TextDataFormat>.</span><span class="sxs-lookup"><span data-stu-id="be57f-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="be57f-132">El código siguiente escribe la cadena "This is a test string" en el Portapapeles como texto RTF.</span><span class="sxs-lookup"><span data-stu-id="be57f-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 <span data-ttu-id="be57f-133">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> para escribir datos en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="be57f-134">En este ejemplo se escribe el `DataObject` `dataChunk` en el Portapapeles con el formato personalizado `specialFormat`.</span><span class="sxs-lookup"><span data-stu-id="be57f-134">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 <span data-ttu-id="be57f-135">Use el método <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> para escribir datos de audio en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="be57f-136">Este ejemplo crea la matriz de bytes `musicReader`, lee el archivo `cool.wav` que hay dentro y lo escribe en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="be57f-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> <span data-ttu-id="be57f-137">Dado que otros usuarios pueden acceder al Portapapeles, no lo use para almacenar información confidencial, como contraseñas o datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="be57f-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be57f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="be57f-138">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [<span data-ttu-id="be57f-139">Cómo: Leer datos de objetos en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="be57f-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="be57f-140">Cómo: Escribir datos de objeto en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="be57f-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
