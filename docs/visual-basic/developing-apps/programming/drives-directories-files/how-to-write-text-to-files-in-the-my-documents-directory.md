---
title: "Cómo: Escribir texto en archivos del directorio Mis documentos en Visual Basic"
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
- files, writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files, in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
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
ms.openlocfilehash: c900072d184469ead75bb76a3e152edce357a34f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="54fa1-102">Cómo: Escribir texto en archivos del directorio Mis documentos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54fa1-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="54fa1-103">El objeto `My.Computer.FileSystem.SpecialDirectories` le permite tener acceso a los directorios especiales, como el directorio **MyDocuments**.</span><span class="sxs-lookup"><span data-stu-id="54fa1-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="54fa1-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="54fa1-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="54fa1-105">Para escribir nuevos archivos de texto en el directorio Mis documentos</span><span class="sxs-lookup"><span data-stu-id="54fa1-105">To write new text files in the My Documents directory</span></span>  
  
1.  <span data-ttu-id="54fa1-106">Use la propiedad `My.Computer.FileSystem.SpecialDirectories.MyDocuments` para proporcionar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="54fa1-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     <span data-ttu-id="54fa1-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="54fa1-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="54fa1-108">Use el método `WriteAllText` para escribir texto en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="54fa1-108">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     <span data-ttu-id="54fa1-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="54fa1-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="54fa1-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54fa1-110">Example</span></span>  
 <span data-ttu-id="54fa1-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="54fa1-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54fa1-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="54fa1-112">Compiling the Code</span></span>  
 <span data-ttu-id="54fa1-113">Reemplace `test.txt` por el nombre del archivo en el que quiere escribir.</span><span class="sxs-lookup"><span data-stu-id="54fa1-113">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="54fa1-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="54fa1-114">Robust Programming</span></span>  
 <span data-ttu-id="54fa1-115">Este código vuelve a producir todas las excepciones que pueden ocurrir al escribir texto en el archivo.</span><span class="sxs-lookup"><span data-stu-id="54fa1-115">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="54fa1-116">Puede reducir la probabilidad de que se produzcan excepciones usando los controles de Windows Forms como los componentes [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) y [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md), que limitan las opciones del usuario a los nombres de archivo válidos.</span><span class="sxs-lookup"><span data-stu-id="54fa1-116">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="54fa1-117">En cambio, el uso de estos controles no es infalible.</span><span class="sxs-lookup"><span data-stu-id="54fa1-117">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="54fa1-118">El sistema de archivos puede cambiar entre el momento en el que el usuario selecciona un archivo y el momento en el que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="54fa1-118">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="54fa1-119">Por ello, cuando se trabaja con archivos casi siempre es prácticamente necesario realizar un control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="54fa1-119">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="54fa1-120">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="54fa1-120">.NET Framework Security</span></span>  
 <span data-ttu-id="54fa1-121">Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="54fa1-121">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="54fa1-122">Para obtener más información, vea [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="54fa1-122">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
 <span data-ttu-id="54fa1-123">En este ejemplo se crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="54fa1-123">This example creates a new file.</span></span> <span data-ttu-id="54fa1-124">Si una aplicación necesita crear un archivo, precisará permisos de creación para la carpeta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="54fa1-124">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="54fa1-125">Los permisos se establecen usando listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="54fa1-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="54fa1-126">Si el archivo ya existe, la aplicación solo necesitará permiso de escritura, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="54fa1-126">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="54fa1-127">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo privilegios de lectura en un solo archivo, en lugar de privilegios de creación para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="54fa1-127">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="54fa1-128">También es más seguro escribir datos en carpetas de usuario en lugar de en la carpeta raíz o en la carpeta **Archivos de programa**.</span><span class="sxs-lookup"><span data-stu-id="54fa1-128">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="54fa1-129">Para obtener más información, vea [Información general sobre la tecnología ACL](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="54fa1-129">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fa1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="54fa1-130">See Also</span></span>  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>

