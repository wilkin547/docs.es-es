---
description: 'Más información acerca de: Procedimiento: para leer texto de archivos con StreamReader (Visual Basic)'
title: Procedimiento para leer texto de archivos con StreamReader
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 9a2eb08209a2a65f7be846c8cb5357978a48ed73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797424"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="a9f50-103">Cómo: Leer texto de archivos con StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9f50-103">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>

<span data-ttu-id="a9f50-104">El objeto `My.Computer.FileSystem` proporciona métodos para abrir un <xref:System.IO.TextReader> y un <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="a9f50-104">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="a9f50-105">Estos métodos, `OpenTextFileWriter` y `OpenTextFileReader`, son métodos avanzados que no aparecen en IntelliSense a menos que seleccione la pestaña **Todos**.</span><span class="sxs-lookup"><span data-stu-id="a9f50-105">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="a9f50-106">Para leer una línea de un archivo con un lector de texto</span><span class="sxs-lookup"><span data-stu-id="a9f50-106">To read a line from a file with a text reader</span></span>  
  
- <span data-ttu-id="a9f50-107">Use el método `OpenTextFileReader` para abrir el <xref:System.IO.TextReader>, especificando el archivo.</span><span class="sxs-lookup"><span data-stu-id="a9f50-107">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="a9f50-108">En este ejemplo se abre el archivo denominado `testfile.txt`, lee una línea del mismo y la muestra en un cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a9f50-108">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a9f50-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a9f50-109">Robust Programming</span></span>  

 <span data-ttu-id="a9f50-110">El archivo que se lee debe ser un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a9f50-110">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="a9f50-111">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a9f50-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="a9f50-112">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a9f50-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="a9f50-113">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f50-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="a9f50-114">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="a9f50-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a9f50-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9f50-115">.NET Framework Security</span></span>  

 <span data-ttu-id="a9f50-116">Para leer un archivo, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="a9f50-116">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="a9f50-117">Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="a9f50-117">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="a9f50-118">Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="a9f50-118">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span> <span data-ttu-id="a9f50-119">El usuario también necesita acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="a9f50-119">The user also needs access to the file.</span></span> <span data-ttu-id="a9f50-120">Para obtener más información, vea [Información general sobre la tecnología ACL](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a9f50-120">For more information, see [ACL Technology Overview](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f50-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f50-121">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [<span data-ttu-id="a9f50-122">Componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a9f50-122">SaveFileDialog Component</span></span>](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms)
- [<span data-ttu-id="a9f50-123">Lectura de archivos</span><span class="sxs-lookup"><span data-stu-id="a9f50-123">Reading from Files</span></span>](reading-from-files.md)
