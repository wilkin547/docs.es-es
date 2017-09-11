---
title: "Cómo: Leer texto de archivos con StreamReader (Visual Basic)"
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
- reading files, text
- text, reading from files
- reading text from files
- files, reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
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
ms.openlocfilehash: d895b32b1613462a6c8dedcc19040b5040f936ec
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="64f84-102">Cómo: Leer texto de archivos con StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64f84-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>
<span data-ttu-id="64f84-103">El objeto `My.Computer.FileSystem` proporciona métodos para abrir un <xref:System.IO.TextReader> y un <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="64f84-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="64f84-104">Estos métodos, `OpenTextFileWriter` y `OpenTextFileReader`, son métodos avanzados que no aparecen en IntelliSense a menos que seleccione la pestaña **Todos**.</span><span class="sxs-lookup"><span data-stu-id="64f84-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="64f84-105">Para leer una línea de un archivo con un lector de texto</span><span class="sxs-lookup"><span data-stu-id="64f84-105">To read a line from a file with a text reader</span></span>  
  
-   <span data-ttu-id="64f84-106">Use el método `OpenTextFileReader` para abrir el <xref:System.IO.TextReader>, especificando el archivo.</span><span class="sxs-lookup"><span data-stu-id="64f84-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="64f84-107">En este ejemplo se abre el archivo denominado `testfile.txt`, lee una línea del mismo y la muestra en un cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="64f84-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     <span data-ttu-id="64f84-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="64f84-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="64f84-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="64f84-109">Robust Programming</span></span>  
 <span data-ttu-id="64f84-110">El archivo que se lee debe ser un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f84-110">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="64f84-111">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="64f84-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="64f84-112">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="64f84-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="64f84-113">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64f84-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="64f84-114">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="64f84-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="64f84-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="64f84-115">.NET Framework Security</span></span>  
 <span data-ttu-id="64f84-116">Para leer un archivo, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="64f84-116">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="64f84-117">Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="64f84-117">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="64f84-118">Para obtener más información, vea [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="64f84-118">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span> <span data-ttu-id="64f84-119">El usuario también necesita acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="64f84-119">The user also needs access to the file.</span></span> <span data-ttu-id="64f84-120">Para obtener más información, vea [Información general sobre la tecnología ACL](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="64f84-120">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f84-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="64f84-121">See Also</span></span>  
 <span data-ttu-id="64f84-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="64f84-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="64f84-123"><xref:System.Windows.Forms.OpenFileDialog></span><span class="sxs-lookup"><span data-stu-id="64f84-123"><xref:System.Windows.Forms.OpenFileDialog></span></span>   
 <span data-ttu-id="64f84-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="64f84-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="64f84-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span><span class="sxs-lookup"><span data-stu-id="64f84-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span></span>   
 <span data-ttu-id="64f84-126">[Componente SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span><span class="sxs-lookup"><span data-stu-id="64f84-126">[SaveFileDialog Component](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span></span>  
 [<span data-ttu-id="64f84-127">Leer archivos</span><span class="sxs-lookup"><span data-stu-id="64f84-127">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)

